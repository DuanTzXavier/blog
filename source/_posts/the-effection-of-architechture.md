---
title: 移动端框架的作用
date: 2016-11-11 16:38:41
tags:
---
# 移动端框架的作用
基础的框架可以让程序比较清晰，但随着业务不断的繁重，框架可以让程序把冗余的代码不断的减少，并且实现清晰的逻辑
## 框架需要实现的逻辑
* 业务分离
	首先是业务分离，因为当应用的业务不断拓张，业务逻辑会不断的复杂，如果没有业务分离的话会使得各个不同的业务部门业务逻辑混杂。当业务逻辑分离可以使各个部门游刃有余的使用自己业务部门的业务逻辑。
* 逻辑分离
	逻辑分离，是指的业务逻辑和UI、网络请求之间的分离，而这其中还有很多的细小分类，这些东西做的好的话，可以使业务分离后的代码调用清晰。
* 公共封装
	* 公共控件封装
		公共空间的封装很重要，因为一个控件的重用性强的话可以使代码量减少很多，不过其实控件的重用性强不强还是得看产品的规划。
	* 公共服务封装
		公共服务包括了很多东西，比如公共埋点，公共报错处理。在公共报错处理上，Bugly做的很好。
	* 公共请求封装
		一个App的请求有百分之九十都是同一个类型的，框架需要把自己App的大部分请求包含到，使自己的请求服务最大化的重用。
	* 公共方法封装
		移动端的开发中，有很大一部分是调整UI，以及关于UI的东西，将这些东西封装好可以使代码的使用率大大提高。
	* 公共通讯封装
		公共通讯指的不是Native与服务端的通讯，而是与移动端的ReactNative和Hybrid之间的通讯。这是框架最需要提供的方法。
