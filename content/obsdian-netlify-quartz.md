---
title: 利用Quartz+netlify搭建数字花园
description: 
date: 2025-08-14 10:58
tags:
  - 项目
---
## 创建 Quartz项目

Clone Quartz 项目到本地，并创建（[参考源](https://quartz.jzhao.xyz/#-get-started)）

```
git clone https://github.com/jackyzha0/quartz.git
cd quartz
npm i
npx quartz create
```

注意：Quartz 至少使用 Node v22 和 npm v10.9.2 才能正常运行。

在本地运行 Quartz 网站服务

```
npx quartz build --serve
```


在自己的 [GitHub](https://github.com) 上创建一个空项目（不要勾选默认创建 README、license、gitignore）。

![[wechat_2025-08-14_160754_640.jpg]]

复制远程仓库的 URL，打开终端，进入 Quartz 文件夹的根目录，运行以下命令（将 `REMOTE-URL`替换为你在上一步复制的 URL）。

![[wechat_2025-08-14_161024_688.png]]

```
git remote -v
git remote set-url origin REMOTE-URL
```

同步内容以将其上传到你的仓库，会将你的内容首次推送到仓库。

```
npx quartz sync --no-pull
```

如果遇到 403 报错，解决办法：

1. 打开 [GitHub Personal Access Tokens 设置](https://github.com/settings/tokens)，新建一个 Fine-grained tokens
2. Repository access 选择 Only select repositories，然后勾选新创建的空项目
3. 确保勾选：
	- Contents → Read and write
	- Actions → Read and write
	- Workflow → Read and write
4. 把这个新 token 配到本地：
```
git remote set-url origin https://<TOKEN>@github.com/huangyangme/diary.git
```
5. 再执行 
```
npx quartz sync --no-pull
```

以后每次想要将更新推送到你的仓库时，只需运行：

```
npx quartz sync
```

## 部署到 [Netlify](https://www.netlify.com/)

点「Add new project」-「Import an existing project」，然后选择 GitHub 的那个项目。

Build settings:
- Publish directory → `public`
- Build command → `npx quartz build`

部署完成（显示绿色域名）后，打开网站预览 xxxx.netlify.app