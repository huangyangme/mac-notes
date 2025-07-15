---
title: macOS 降级指南
description: 
date: 2025-07-15 10:59
tags:
---
## 降级前需知：

- macOS 降级抹掉Mac的磁盘数据
- 只能安装你这台Mac支持的 macOS 版本

## 准备

准备一个移动硬盘（官方建议至少要有14GB可用储存空间），抹掉成「macOS扩展日志式」，磁盘名字建议为 `MyVolume`。

[下载旧版本 macOS](https://apps.apple.com/cn/story/id1784326336)/

使用终端命令创建可引导安装器

`sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`

有一些是 Apple T2 安全芯片的 Mac（注意是 T2 安全芯片，不是 M2 芯片），还需要先开启「允许从外部介质启动」。以下这些是配备了 Apple T2 安全芯片的 Mac。

T2:[https://support.apple.com/zh-cn/HT208198](https://support.apple.com/zh-cn/HT208198)

M：[https://support.apple.com/zh-cn/guide/mac-help/mchl768f7291/mac](https://support.apple.com/zh-cn/guide/mac-help/mchl768f7291/mac)

[https://support.apple.com/zh-cn/HT208862](https://support.apple.com/zh-cn/HT208862 "搭载 Apple T2 安全芯片的 Mac 机型")


## 正式安装

在终端执行命令报如下错误时：

> APFS disks may not be used as bootable install media.
> An error occurred erasing the disk.

原因是并没有新建独立卷宗来制作安装器，而是在原有卷宗添加新卷宗。

解决办法，创建独立新卷宗（其他备用宗卷）。

[https://iboysoft.com/news/apfs-disks-may-not-be-used-as-bootable-install-media.html](https://iboysoft.com/news/apfs-disks-may-not-be-used-as-bootable-install-media.html)

[https://support.apple.com/zh-cn/HT201372](https://support.apple.com/zh-cn/HT201372)
[https://support.apple.com/zh-cn/HT211683](https://support.apple.com/zh-cn/HT211683)
[https://support.apple.com/zh-cn/HT204904](https://support.apple.com/zh-cn/HT204904)
