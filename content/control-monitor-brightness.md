---
title: 如何用键盘控制Studio Display以及其他三方显示屏的亮度？
description: 越来越多的第三方键盘针对 Mac 做了适配，比如用 F1 来调暗MacBook屏幕亮度，但是如果你搭配的是Studio Display，会发现这样操作无效。
date: 2025-07-09T17:56:00
tags:
  - 鼠键
---

## 方法一：把键盘上屏幕调暗、调亮键映射为 F14、F15

打开 macOS 系统设置-键盘-键盘快捷键，点左边栏的「显示器」，后面可以定义降低和提高显示器亮度的快捷键，默认是 `F14` 和 `F15`。

![[Screenshot 2025-07-11 09.43.23.jpg]]

把键盘的亮度调低和亮度调高键分别映射到 `F14` 和 `F15`上就搞定了。

我的 MelGeek O2 这只键盘可以用 MelGeek 官方软件 [MelGeekHive](https://www.melgeek.cn/download) 来修改键位映射。但是这里只能选择 `F1` 到 `F12`，没有`F14` 和 `F15`。

![[Screenshot 2025-07-11 09.42.49.jpg]]

那就改一下 macOS 上的默认键吧。把降低显示器亮度键改为 F1，把提高显示器亮度键改为 F2。

![[Screenshot 2025-07-11 09.44.35.jpg]]

再把键盘的调暗和调亮键分别映射为 `F1`和`F2`，这样就能直接按键盘上这两个键来调节 Studio Display 的显示亮度了，体验就跟用原生键盘一样。


![[Screenshot 2025-07-11 10.49.53.jpg]]
## 方案二：安装 MonitorControl 这个软件

安装 [MonitorControl](https://github.com/MonitorControl/MonitorControl)，搞定！

![[IMG_2741.gif]]

类似软件还有 [BetterDisplay](https://github.com/waydabber/BetterDisplay) 

