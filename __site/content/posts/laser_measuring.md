---
title: "Laser_measuring 基恩士激光测量仪EAP系统"
description: "基恩士 TM-3000 激光测量仪管理系统"
date: 2020-04-10T20:55:32+08:00
draft: false
author: Liuzhongwu
categories: ["案例"]
tags: ["工厂技改项目","DotNet_Framework","CSharp"]
---

 

## 项目简介
客户：某世界500强医疗器械公司苏州工厂。   
为客户定制开发了一套基恩士 TM-3000 测量仪配套的管理系统，反馈不错。 如果有谁需要定制开发，可以联系我，`liuzhongwu2008@163.com.`

## 关于基恩士 TM-3000 激光量测仪
首先介绍一下基恩士公司 (keyence 公司) 的 TM-3000 激光量测仪，非接触式测量，应用场合很广，  官方产品主页是: <http://china.keyence.com/products/measure/micrometer/tm-3000/index.jsp> . 该系统产品运用了透射原理，且测量范围大，调节不费时间，缩短了装置操作工时。 测量指标非常高:
  - 同时可以测量 16 个点，
  - 重复精度：正负 0.06 微米
  - 测量位置精度，正负 0.5 微米

也许有人知道基恩士官方提供了 TM Navigator 软件，可能会认为这个软件可以做量测管理系统，其实是不行的。该软件仅是用来制作测量程式的。举个例子，我们要测量一个产品的长宽高，先用 TM Navigator 软件制作一个针对这个产品的测量长宽高的程式，在量测的时候，需要将这个程式上传到测量仪控制器，然后再手动操控测量仪进行测量，然后再手动将测量值抄录下来.
 
从这个过程中，我们可以发现，测量程式可以由 TM Navigator 完成，但测量过程还是需要很多手工操作，如果你的产品比较多，或者同一个产品，型号比较多，你就需要一个管理系统了，如果产品批量很大，这些手动操作就显得非常麻烦了。这也是 TM Plus 量测管理系统最原始的需求. 

![](../laser_measuring_files/1.jpg)

## TM Plus 量测管理系统(Equipment automation program)
也许你会问，既然管理系统这么有用，为何基恩士公司 (keyence 公司) 自己不开发一套测量管理系统？  答案是成本考量， 每个客户的管理流程都不一样，报告格式不一样，比较大的客户都有专门的测量数据库，这又涉及到数据接口的问题，所以即使是专门针对 TM-3000 的管理系统也不可能做成一个标准化的产品，都要定制开发，对于基恩士公司这样的公司，这样成本一下就上去了.

在这个管理系统的开发过程中，参考了基恩士公司提供的产品 pdf 手册和编程 api 手册，不得不说，日本公司东西做得真是极致，硬件就不说了，文档写的真好，pdf 文档相关章节可以来回跳转，对于了解产品太有帮助了.

下面是我开发的 TM Plus 量测管理系统的主要功能:
  - 可根据产品型号自动调用 TM-3000 测量程序
  - 产品件序列号可自动生成或条码扫描输入
  - 支持产品件返工后重测
  - 尺寸超限自动报警提示 (蜂鸣 / 界面高亮)
  - 可生成批次测量报告 (pdf 格式或纸张打印)
  - 完善的权限控制和日志功能
	
下面是主界面的截图，后面的链接是管理系统的介绍文档, 
![](../laser_measuring_files/2.jpg)


如果您有类似需求，可以联系我，`liuzhongwu2008@163.com`