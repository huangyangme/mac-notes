---
title: 跟Ghost自建博客网站有关的
description: 
date: 2025-08-13 21:26
tags:
  - 软件
---

## 在腾讯云主机搭建 Ghost 网站

在腾讯云购买==轻量应用服务器（基于Ubuntu 22操作系统镜像）==，选择海外（香港或东京）主机可以免备案。  

打开服务器后台，绑定自己的域名解析。登录。  

现在安装 Ghost 非常简单，按照 [Ghost 官网的教程](https://ghost.org/docs/install/ubuntu/)一步步安装即可，不需要任何手动配置。  

## 备份 Ghost 网站

进入网站目录，如 `/var/www/blog`

运行备份命令 `ghost backup`

会生成备份文件放在网站根目录，文件名如 `backup-from-v5.103.0-on-2024-12-18-14-13-35.zip`，下载zip备份文件即可。

相关内容： [https://ghost.org/docs/faq/manual-backup/](https://ghost.org/docs/faq/manual-backup/)

## 如何修改文章路由地址？

Ghost 默认文章地址如是： `huangyang.me/xxx`
希望改成： `huangyang.me/blog/xxx`

可以在 `content/settings/routes.yaml` 中修改 `collections.permalink` 为 `/blog/{slug}/`

![[taxonomies.jpg]]

## 二次开发Ghost默认博客主题
  
1. 在[本地安装Ghost](https://ghost.org/docs/install/local/)
2. 复制（或下载）默认主题，并放在本地项目的 Themes 文件夹下。  
3. 修改开发主题的文件夹名称，以及主题根目录下的 package.json 文件的主题名定义。
4. 启动本地 Ghost 网站，并把开发主题作为使用主题。
5. 根据主题目录内的 RAEDME 文件说明，把命令行到开发主题目录，使用 `yarn install` 和 `yarn dev` 来编译本地 css 文件的修改。
6. 通过 `yarn zip` 编译并打包主题
7. 把打包的主题文件上传到 Ghost 网站后台并使用即可。

[Ghost Handlebars Themes](https://ghost.org/docs/themes/)