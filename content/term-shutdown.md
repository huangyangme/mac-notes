---
title: Mac 如何通过终端命令关机？
description: 
date: 2025-07-14T11:15:00
tags:
  - 小技巧
---

打开「终端」工具，输入或粘贴相关文本命令并回车，输入Mac登录密码（非Apple ID密码）并回车即可。

![[WX20241012-171121@2x.490b9822e0f1448db68f8872fbeeda73.png]]
立即关机：

`sudo shutdown -h now`

或：

`sudo halt`


10分钟后关机：

`sudo shutdown -h +10`

晚上8点关机：

`sudo shutdown -h 20:00`


立即重启：

`sudo shutdown -r now`

或：

`sudo reboot`


设定 2024年12月01日15:00 关机：

`sudo shutdown -h 2412011500`

  

同理，设定 2024年12月11日15:00 重启：

`sudo shutdown -r 2412011500`
  

> [!important] 解释：`shutdown`（关闭）这个命令用来操作 Mac 的开关状态的，-h/-r/-s 分别代表：关机/重启/睡眠，最后加上时间。

没有鼠标怎么让Mac关机？[[no-mouse-shutdown]]

相关阅读：[在“终端”中设置 Mac 定时开关机](https://support.apple.com/zh-cn/guide/mac-help/mchl40376151/mac?ref=macpai.cn)