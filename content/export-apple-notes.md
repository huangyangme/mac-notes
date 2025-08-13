---
title: 完整导出苹果备忘录笔记
description: 
date: 2025-07-14T11:16:00
tags:
  - 软件
  - 效率
---
macOS 的备忘录 App 的菜单栏导出功能（菜单栏-文件-导出为PDF）只支持导出单篇笔记，且只能导出为 PDF 格式。

## 苹果官网打包导出（txt格式，耗时长）

Apple ID 下的用户数据都可以在苹果官网打包下载，用浏览器打开 [https://privacy.apple.com](https://privacy.apple.com/?ref=macpai.cn) 并登录。点「请求获取数据副本」，选择“iCloud备忘录”即可下载。

## 第三方工具导出

不想等待那么久，也可以使用第三方工具来导出，比如 [Exporter](https://apps.apple.com/cn/app/exporter/id1099120373?mt=12)（可以在 Mac App Store 免费下载）。

用 Exporter 导出前还可以**设置导出笔记命名规则和 Markdown 格式**。

用 Exporter 成功导出的笔记是 Markdown 格式，正文语法也会转化成 Markdown 语法，非常适合迁出至支持 Markdown 的笔记平台。

## 导出整个备忘录数据库

备忘录数据库保存在 `'/Users/huangyang/Library/Group Containers/group.com.apple.notes'` 位置，把整个 `group.com.apple.notes` 文件夹拷贝到其他地方（比如移动硬盘），算是一种备份。

## Automator Workflow（from Bear app）

另外，[Bear app](https://bear.app) 官方也提供了导出备忘录笔记的 [Automator Workflow](https://bear.app/faq/migrate-from-apple-notes/)。


## ProNotes

[ProNotes](https://www.pronotes.app) 虽然不能帮助导出备忘录笔记，但它是一款 Mac 备忘录 app 增强扩展工具，可以让 Mac 备忘录支持 Markdown、类似 Notion 的斜杠命令、模版等，值得一提。

PS：Apple OS 26 开始，Notes 支持 markdown 的导入和导出。