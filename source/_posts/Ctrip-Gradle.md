---
title: Ctrip-Gradle
date: 2016-11-04 15:04:13
tags:
---
# The Gradle File of Ctrip
现如今，大公司很推崇各个部门业务模块分离，这也就使旗下各个研发部相互分离。而Gradle分模块编译可以使业务逻辑分离。这也就恰巧应了当下环境的景。今天我简单浅析一下Ctrip Gradle是如何实现业务之间分离的。
## 模块划分
首先最重要的就是模块的划分，因为业务模块的繁多，而且近些年来H5 Hybrid以及ReactNative的兴起，并不是Android中全部业务逻辑都是用Native方式所写，所以最终要的一个分支就是基础框架模块，在Ctrip中叫CTBusiness。
基础框架划分完以后就是业务框架了，因为Ctrip分有公共业务和非公共业务，比如预定各种东西（无论是机票火车票还是酒店）都需要付款，所以就衍生出来一个公共的业务逻辑模块--支付（CTPay）。
接下来就是各个业务部的各个逻辑了，比如有旅行（CTTour），酒店（CTHotel），机票（CTFilght）等等的模块。
**总结**：
* 基础框架模块：负责各个业务模块调用以及Native，H5 Hybrid，ReactNative相互调用
* 支付模块：负责提供基础业务
* 其他模块：负责提供自己业务部门的业务逻辑
> TIPS： 当然，你还需要一个起吊模块

## Gradle File主要逻辑
写过自定义控件或者Library的同学都应该知道，当你的module编译完成以后发到JCenter的文件其实是.pom和.aar，而.pom其实是一个配置文件，.aar才是最终所需要的。Ctrip就是利用了这一点，如果我是维护CTBusiness的话，我只需要让CTBussiness编译就可以了，其他业务逻辑的东西可以直接编译aar文件让整个程序跑起来。

### Main.gradle
这是Ctrip最重要的模块，没有之一，他控制了是否对于