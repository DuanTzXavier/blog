---
title: 消除当View设置VISIBLE、GONE时的残影
date: 2016-11-11 14:15:59
tags:
---
# 消除当View设置VISIBLE、GONE时的残影
## 背景
现有一需求：点击RecycleView时Item高度比Item本身长
解决办法： 在RecycleView的Item上覆盖一个View，作为临时Item，此Item高度可以任意定制，只要可以覆盖住后面的Item即可，点击的时候现实，放开的时候消失。并获取Item的位置，然后根据Item的位置设置临时Item的位置。
疑点： 当点击Item获取到此Item的位置，设置临时Item的位置，并将临时Item设置为现实的时候，视觉可以感受到设置之前的残影。此为Android效率问题，证明Android在设置View位置的速度比设置其现实还是隐藏更慢，无论代码是怎么写。

## 解决方法
> 利用Android的FrameLayout
* 在每次设置View（临时Item）为隐藏的同时将Recycleview置于顶层，覆盖住View。
* 在每次设置View（临时Item）位置，并设置其为显示状态之后，设置此View置于顶层，覆盖在Recycleview之上。

## 综合总结
这样写虽然没有使Android的效率加快，但是完美解决了残影问题。