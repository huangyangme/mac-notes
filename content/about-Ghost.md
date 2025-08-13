---
title: 跟Ghost自建博客网站有关的
description: 
date: 2025-08-13 21:26
tags:
  - 软件
---

## 二次开发Ghost默认博客主题
  
1. 在[本地安装Ghost](https://ghost.org/docs/install/local/)
2. 复制（或下载）默认主题，并放在本地项目的 Themes 文件夹下。  
3. 修改开发主题的文件夹名称，以及主题根目录下的 package.json 文件的主题名定义。
4. 启动本地 Ghost 网站，并把开发主题作为使用主题。
5. 根据主题目录内的 RAEDME 文件说明，把命令行到开发主题目录，使用 `yarn install` 和 `yarn dev` 来编译本地 css 文件的修改。
6. 通过 `yarn zip` 编译并打包主题
7. 把打包的主题文件上传到 Ghost 网站后台并使用即可。

[Ghost Handlebars Themes](https://ghost.org/docs/themes/)