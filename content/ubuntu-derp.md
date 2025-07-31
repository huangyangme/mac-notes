---
title: 腾讯云 Ubuntu 22.04 自建 DERP 服务器终极指南
description: 
date: 2025-07-31 10:35
tags:
---

以下是 **更详细的腾讯云 Ubuntu 22.04 自建 DERP 服务器终极指南**，从零开始手把手教学，包含每一步的详细解释、截图位置和故障排查方法：

---- 

### **一、腾讯云基础配置（含截图指引）**
1. **购买与登录服务器**
   2. 进入腾讯云控制台 → 云服务器 → 新建实例
   3. 选择配置（最低推荐）：
	 - 地域：靠近用户的区域（如华东-上海）
	 - 镜像：Ubuntu 22.04 LTS
	 - 实例规格：2核2GB（突发性能实例t6约￥60/月）
	 - 安全组：**提前放行TCP 443、UDP 3478**（位置：安全组 → 入站规则）
   4. 设置SSH密钥登录（比密码更安全）

5. **域名解析（以腾讯云DNSPod为例）**
   6. 进入DNSPod控制台 → 你的域名 → 添加记录：
	 - 主机记录：`derp`（最终域名为 `derp.yourdomain.com`）
	 - 记录类型：A
	 - 记录值：服务器公网IP
   7. 验证解析是否生效：
	```bash
	ping derp.yourdomain.com
	# 应返回服务器IP
	```

---

### **二、服务器初始化（逐条命令解释）**
```bash
# 1. 更新系统（所有提示输入Y的地方直接按回车确认）
sudo apt update && sudo apt upgrade -y

# 2. 安装Docker（官方推荐部署方式）
sudo apt install -y docker.io docker-compose
sudo systemctl enable --now docker

# 3. 验证Docker安装
sudo docker ps  # 应返回空列表无报错

# 4. 创建专用网络（隔离容器）
sudo docker network create tailscale-net
```

---

### **三、Tailscale客户端配置（关键步骤详解）**
1. **启动Tailscale容器（用于设备认证）**
```bash
sudo docker run -d --name=tailscale \
  --network=tailscale-net \
  --volume=/var/lib/tailscale:/var/lib/tailscale \
  --volume=/dev/net/tun:/dev/net/tun \
  --cap-add=NET_ADMIN \
  --cap-add=NET_RAW \
  --restart=always \
  tailscale/tailscale tailscaled
```

2. **登录认证（必须步骤）**
   3. 执行以下命令获取认证链接：
	```bash
	sudo docker exec -it tailscale tailscale up --advertise-exit-node
	```
   4. 终端会返回类似：
	```
	Please visit: https://login.tailscale.com/a/abcdef123
	```
   5. **浏览器打开链接** → 登录你的Tailscale账号 → 授权设备

6. **验证节点上线**
   7. 进入Tailscale管理面板 → Machines
   8. 应看到你的服务器已在线，并有 `exit-node` 标签

---

### **四、DERP服务器部署（含证书自动申请）**
1. **启动DERP容器（重点参数说明）**
```bash
sudo docker run -d --name=derper \
  --network=tailscale-net \
  -p 443:443 -p 3478:3478/udp \
  -e DERP_HOSTNAME=derp.yourdomain.com \
  -e DERP_CERT_MODE=letsencrypt \       # 自动申请SSL证书
  -e DERP_ADDR=:443 \                   # 监听443端口
  -e DERP_VERIFY_CLIENTS=true \         # 只允许Tailscale网络设备连接
  --restart=always \
  -v /var/lib/tailscale:/var/run/tailscale \  # 共享Tailscale认证
  tailscale/derper
```

2. **验证部署成功**
   3. 查看实时日志：
	```bash
	sudo docker logs -f derper
	```
   4. 成功时会出现：
	```
	derper: serving on :443 with TLS
	```
   5. 访问测试：
	```bash
	curl https://derp.yourdomain.com
	# 应返回 "DERP" 欢迎页面
	```

---

### **五、Tailscale网络配置（图文对应）**
1. **修改ACL策略文件**
   2. 进入Tailscale Admin Console → Access Controls
   3. 在JSON配置中添加（位置通常在文件顶部）：
	```json
	"derpMap": {
	  "Regions": {
	    "901": {
	      "RegionID": 901,
	      "RegionCode": "tencent-sh",
	      "RegionName": "Tencent Shanghai",
	      "Nodes": [{
	        "Name": "1",
	        "RegionID": 901,
	        "HostName": "derp.yourdomain.com",
	        "DERPPort": 443,
	        "STUNPort": 3478
	      }]
	    }
	  }
	}
	```
   4. 点击Save保存

5. **客户端强制更新配置**
```bash
# 在所有客户端设备上执行
sudo tailscale up --reset
```

---

### **六、验证与监控（实用命令集）**
1. **测试中继是否生效**
```bash
tailscale netcheck
# 输出应包含：
# * your region (tencent-sh) - 15ms
# DERP map:
#   tencent-sh: derp.yourdomain.com:443 (...)
```

2. **模拟NAT穿透失败测试**
```bash
tailscale ping --verbose --derp-only <另一台设备别名>
# 应通过你的DERP服务器中转
```

3. **监控流量**
```bash
sudo docker stats derper  # 查看CPU/内存/网络占用
```

---

### **七、故障排查大全**

| 问题现象    | 检查步骤                             | 解决方案                                                                        |
| ------- | -------------------------------- | --------------------------------------------------------------------------- |
| 证书申请失败  | `docker logs derper` 查看日志        | 1. 确认域名解析生效<br>2. 确保443端口未被占用<br>3. 尝试手动模式：`DERP_CERT_MODE=manual` + 手动放置证书 |
| 客户端无法连接 | `telnet derp.yourdomain.com 443` | 1. 检查腾讯云安全组<br>2. 确认 `DERP_VERIFY_CLIENTS=false` 测试                         |
| 延迟过高    | `mtr derp.yourdomain.com`        | 1. 更换服务器地域<br>2. 检查BGP路由（企业用户可申请弹性公网IP）                                     |

---

### **八、高级优化（生产环境建议）**
1. **启用TCP BBR加速**
```bash
echo "net.core.default_qdisc=fq" | sudo tee -a /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" | sudo tee -a /etc/sysctl.conf
sudo sysctl -p
```

2. **定时更新容器**
```bash
# 每周凌晨3点自动更新
(crontab -l ; echo "0 3 * * 0 docker pull tailscale/derper && docker restart derper") | crontab -
```

3. **备份配置**
```bash
# 备份Tailscale密钥和DERP配置
sudo tar czvf derp-backup.tar.gz /var/lib/tailscale /var/lib/docker/volumes
```

---

按照以上步骤操作后，你将获得一个企业级可用的私有DERP服务器。如果遇到任何问题，可随时通过 `docker logs derper` 获取详细错误信息进行排查。