---
title: Crash案例分析
date: 2021-02-19 23:00:05
categories: Kernel
tags: Crash
---

# crash案例分析
使用 echo c > /proc/sysrq-trigger 手动构造了crash事件
以此为模板，分析整个Crash的流程

1. 系统
openEuler 20.03 (LTS-SP1)

2. kernel版本
4.19.90-2012.5.0.0054.oe1


## 打开Vmcore文件
