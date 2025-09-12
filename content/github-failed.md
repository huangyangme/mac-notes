---
title: Github Push/Pull 不了代码
description: 
date: 2025-09-12 09:15
tags:
  - 开发
---

Github Push/Pull 不了代码？多是 DNS 污染引起的，可以尝试修改 DNS。

## 1、获取最新的 GitHub 相关域名 IP 地址

访问 [https://www.ipaddress.com/](https://www.ipaddress.com/) 或类似的服务，分别查询 `github.com`、`github.global.ssl.fastly.net`、`assets-cdn.github.com` 等域名当前的 IP 地址。
  

## 2、修改 hosts

打开 `/etc/hosts`，在文件末尾添加👇

```text
# GitHub Start
140.82.112.3    github.com
151.101.1.194   github.global.ssl.fastly.net
185.199.108.153 assets-cdn.github.com
# GitHub End
```:cite[1]

```
  
3、## 刷新 DNS 缓存

终端 `sudo dscacheutil -flushcache` 或 `sudo killall -HUP mDNSResponder`