---
title: 怎么修改 Mac 的 hosts 文件？
description: 
date: 2025-07-14T11:17:00
tags:
  - 小技巧
  - 软件
---
打开访达（Finder）， 选择顶部菜单栏【前往】-【前往文件夹…】，输入 hosts 文件所在的 `/private/etc/` 文件夹目录。

找到 `/private/etc` 文件夹下的 `hosts` 文件（文件较多，可使用右上角搜索）。复制一份到桌面（直接拖拽到桌面即可）。用文本编辑器打开并修改 hosts 文件。修改完保存。

![[8267456565_774877.06b19e9f546d4ad78586fe9fda1cb7f1.jpg]]
回到 Finder 的 `/private/etc/` 文件夹，删除原来的 `hosts`文件，再将桌面修改后的 `hosts`文件拖回文件夹下即可。

如果需要频繁修改 Hosts 文件，这种手动修改的方式就比较麻烦，可以借助第三方工具更方便的修改操作，比如 [iHosts](https://apps.apple.com/cn/app/ihosts-etc-hosts-%E7%BC%96%E8%BE%91%E5%99%A8/id1102004240?mt=12)、[EasyHosts](https://apps.apple.com/cn/app/easyhosts-lite/id6596765507?mt=12)，这两款工具都可以在 Mac App Store 下载。