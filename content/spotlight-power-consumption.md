---
title: macOS聚焦搜索耗电高问题解决办法
description: 
date: 2025-07-14 16:12
tags:
  - 小技巧
  - Mac功耗
---
“聚焦”使用大量能耗解决方案（重建“聚焦”索引）
[https://www.cnblogs.com/Flat-White/p/17019942.html](https://www.cnblogs.com/Flat-White/p/17019942.html)

重建聚焦的索引,建议移动硬盘直接禁止聚焦去搜索
https://support.apple.com/zh-cn/HT201716

重置聚焦后，插电让它执行一晚上，多数情况下检索操作就会完成，然后进程就不会耗能太大了。

补充一点：打开“系统设置” --\> "Spotlight" （聚焦搜索) 切换到Privacy （隐私）选项卡，里面可以将某些文件夹排除在搜索之外，比如你的非常隐私的个人文件，或者内容多大的文件等。

另外，聚焦搜索会检索iCloud上的文件，如果你的文件处于“未下载”的状态，聚焦搜索会先将文件从云端下载以后，再创建索引。