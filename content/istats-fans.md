---
title: 不装软件查看 Mac 温度和风扇转速
date: 2025-07-09 17:43
tags:
  - 小技巧
  - 软件
description: iStats 是一款命令行工具，可让你直接在终端输入命令就能获取 Mac 的风扇速度和电池信息。
---

[iStats](https://github.com/Chris911/iStats) 是一款命令行工具，可让你直接在终端输入命令（istats）就能获取 Mac 的风扇速度和电池信息。

打开「终端」app，输入 `sudo gem install iStats` 并回车，接着输入 Mac 登录密码（输入时候不可见），并再次回车。

下一次想查看 Mac 的温度，只需要**打开终端，输入 `istats` 然后回车**就行了。

![[Screenshot 2025-07-09 17.42.37.jpg]]
如果出现温度或风扇过高，状态显示会变成红色，并且闪动。


安装「[腾讯柠檬清理](https://lemon.qq.com/?ref=macpai.cn)」、「[iStat Menus](https://bjango.com/mac/istatmenus/?ref=macpai.cn)」这类第三方工具也可以查看风扇转速。

**[Macs Fan Control](https://crystalidea.com/macs-fan-control/download)** 这款软件可以自定义 Mac 散热风扇的转速。软件支持免费使用，高级版可以解锁更多自定义功能。