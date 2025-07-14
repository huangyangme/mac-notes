---
title: 把富士相机变成Mac网络摄像头
permalink: 
date: 2025-07-09 16:49
tags:
  - 小技巧
description:
---

通过富士官方软件 FUJIFILM X Webcam 可以实现让部分型号的富士相机作为电脑（PC/Mac）的网络摄像头。

[这些型号的富士相机](https://fujifilm-x.com/zh-cn/support/compatibility/software/x-webcam/)支持 FUJIFILM X Webcam。

首先下载并安装 [FUJIFILM X Webcam 软件](https://fujifilm-x.com/global/support/download/software/x-webcam-macos14-or-later/?ref=macpai.cn#mac)，安装后需重启一次 Mac。

其他版本软件点[这里](https://fujifilm-x.com/global/support/download/software/?ref=macpai.cn)。

## 富士相机上的准备设置（以X-S10为例）

- 模式拨盘转到 S（单张拍摄模式），有些型号相机没有这个模式拨盘，可跳过
- 设置菜单 > 连接设置 > 连接模式：USB TETHER自动（或 X Webcam）
- 设置菜单 > 连接设置 > USB电源设置：开
- 设置菜单 > AF/MF设置 > PRE-AF：开
- 置菜单 > AF/MF设置 > 脸部识别：开
- 置菜单 > AF/MF设置 > AF+MF：开
- 按需调整光圈、快门、IOS

## 如何使用？

下一步用 USB 数据线连接富士相机和 Mac，把相机开机。

打开一款使用摄像头的软件，比如 QuickTime Player（新建录影）、Omi录屏专家、飞书、微信等，再把摄像头切换到 FUJIFILM X Webcam 2 即可。

通过 FUJIFILM X Webcam 2 软件可以调节对焦等功能，甚至使用胶片模拟。

![[Screenshot 2025-07-09 17.21.12.jpg]]
## 缺点

分辨率（画质）只有 1024x768，只适合作为网络摄像头，作为录制采集差点意思（想直接录制 1080P 或 4K 到 Mac 还是得上采集卡）。

![[c57bd4beec87427c8ccfce502ae940d1.jpg]]

## 如何卸载软件（插件）？

从「应用程序」文件夹中删除应用程序，然后在 `MacintoshHD/资源库/CoreMediaIO/Plug-Ins/DAL/` 目录中删除 ` FUJIFILM X Webcam.plugin` 这个文件。

重启一次电脑。

## 其他品牌相机类似功能

佳能相机下载[「EOS Webcam Utility」](https://www.canon.com.cn/special/webcam/index.html)。
``

索尼相机下载[「Imaging Edge Webcam 」](https://support.d-imaging.sony.co.jp/app/webcam/en/)。

尼康相机下载[「Webcam Utility」](https://downloadcenter.nikonimglib.com/zh-cn/products/548/Webcam\_Utility.html)。


官方使用指南：[https://fujifilm-dsc.com/en/manual/webcam/](https://fujifilm-dsc.com/en/manual/webcam/?ref=macpai.cn)
我的视频教程：[https://www.bilibili.com/video/BV1sL4y1A7ie/](https://www.bilibili.com/video/BV1sL4y1A7ie/?spm_id_from=333.337.search-card.all.click&vd_source=2c6d36c198a49221a729c152cec6f972&ref=macpai.cn)