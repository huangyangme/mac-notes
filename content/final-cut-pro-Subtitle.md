---
title: 用 Final Cut Pro 导出带烧录字幕的视频
description: 
date: 2025-07-14T11:02:00
tags:
  - FinalCutPro
---
把 Final Cut Pro 导出不带字幕的视频（可以选低分辨率的，这样快一些），并把导出的视频拖拽到 剪映或MacWhisper 开始自动识别生成字幕，修改调整后，导出 `.srt` 字幕文件。

把 `.srt` 字幕文件导入到 Final Cut Pro 的视频项目中。

![[Pasted Graphic 1.jpg]]

点击轨道上的一个字幕，并 `command-A` 全选字幕，在右上角点格式语言，格式选 SRT，语言也可以点「编辑角色」添加一个中文（如果你是要添加中文语言字幕的话）。

![[Pasted Graphic 5.jpg]]

修改后这个地方会变成 SRT 中文（简体）。

![[Pasted Graphic 7.jpg]]

`Command-E` 导出文件，点「角色」，点「字幕」图标，在弹出选相框的「固定字幕」选择中文（简体SRT）。

![[Pasted Graphic 8.jpg]]

最后点「下一步」导出，就是带烧录字幕的视频文件啦。