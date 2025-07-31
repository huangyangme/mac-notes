---
title: Mac通过「互联网共享」让其他设备零配置科学上网
description: 
date: 2025-07-27 10:21
tags:
  - 经验
---
Mac 上安装 ==Quantumult X==（需要外区Apple ID，并且是付费软件，并且仅支持 Apple silicon Mac），配置好节点并开启，此时这台 Mac 可以科学上网。

![[Screenshot 2025-07-27 16.12.06.jpg]]

打开「系统设置」-「通用」-「共享」，找到「==互联网共享==」，点进去设置。

「共享以下来源的连接」选 Quantumult X，「使用一下端口共享给设备」选 Wi-Fi。

![[Screenshot 2025-07-27 16.17.06.jpg]]

接下来设置共享 Wi-Fi 的密码，安全性建议选 WPA3，密码可以改成你容易记得住的，点「好」，并开启「互联网共享」。

![[Screenshot 2025-07-27 16.16.38.jpg]]


用另外一台设备（比如手机）打开 Wi-Fi 连接，找到 Mac Studio 的 Wi-Fi 名字，点连接并输入密码，就跟正常连 Wi-Fi 一样。然后这台设备就可以自由访问外网了。

参考：[https://hoohoo.top/blog/how-to-share-a-vpn-network-on-your-mac-as-a-source-of-wi-fi-hotspots/](https://hoohoo.top/blog/how-to-share-a-vpn-network-on-your-mac-as-a-source-of-wi-fi-hotspots/)
