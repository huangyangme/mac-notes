---
title: 在Mac上安装使用Windows软件
description: 
date: 2025-07-15 15:58
tags:
  - 虚拟机
  - Windows
---
## Parallels Desktop

Mac 体验最佳的虚拟机软件，_收费_的。使用 PD 安装 Windows 虚拟机的_流程非常简单_，小白也能轻松搞定。

PD 对_性能的优化_（尤其是图形性能）比较好，“_融合模式_”是它的一大特色。

PD 不仅能安装 Windows ARM，还能安装 macOS（可以登录 Apple ID）以及 Lunix 系统。

PD 目前也在开发支持在 Apple 芯片的 Mac 上安装 Windows x86 架构。

## VMware Fusion

Mac 上另一款虚拟机软件，功能跟 PD 类似，好处是_免费_。VM 的安装流程比较复杂，耗时长，需要一定的动手能力。

## utm

免费虚拟化软件，基于开源的 QEMU

效率可能更低，属于“能跑就行”的方案。

可运行 ARM 和 x86 架构系统（仿真 x86 时较慢）

## Crossover

Crossover 跟虚拟机软件运行 Windows 的技术原理不一样，它可以让 macOS 直接运行 Windows 程序，而不需要经由 Windows 系统。

Crossover 更像是为“在 Mac 上玩 Windows 游戏”这种场景而生，对 Windows 软件的兼容性不如 Windows 虚拟机，但对支持的游戏（比如《黑神话悟空》、《赛博朋克2077》优化得有比较好）。

## whisky

		类似 Crossover，开源免费，但已不在维护。