---
title: 查看Mac CPU&GPU运行功耗（不装软件）
permalink: powermetrics
date: 2025-07-08
tags:
  - Mac功耗
  - 小技巧
description: 简短的摘要说明（可选）
---
打开终端，输入 `sudo powermetrics` 并会车，然后输入 Mac 登录密码，就能看到很多 Mac 运行状况的信息。往下翻，找到 CPU Power 和 GPU Power。

![[assets/powermetrics.jpg]]

进程会持续读取最新的运行状况，记得及时关闭（`control + C`）。

另一种方法：[asitop](https://medium.com/@wade3c/asitop-%E7%9B%A3%E6%8E%A7m%E7%B3%BB%E5%88%97%E6%99%B6%E7%89%87mac%E7%9A%84%E9%9B%BB%E6%BA%90%E4%BB%A5%E5%8F%8A%E8%B3%87%E6%BA%90%E4%BD%BF%E7%94%A8%E7%8E%87-c560f3ae4ca9?ref=macpai.cn)