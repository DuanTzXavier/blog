---
title: rxjava
date: 2016-10-24 15:43:41
tags:
---

1. 什么是RxJava
  * reactive extension for the JVM
    为Java虚拟机提供的响应式拓展
  * a library for composing asynchronous and event-based programs using observable sequences for the Java VM
    为Java虚拟机所提供的，使异步和基于事件的程序定型的，用观察者队列的库
    * 为异步程序和基于事件的程序定型
    * 用观察者队列
  * RxAndroid
   适用于Android平台的RxJava插件--封装了handler looper，使得RxJava可以让子线程和Android主线程交互。
   ```
   some code
   ```
2. RxJava的好处
  1. 响应式编程
    * 什么是响应式编程
      * 什么是响应式编程
      * 响应式编程的历史
  2. 形式简洁
  ```
  old code
  ```

  ```
  new style
  ```
  3. 观察者模式

3. RxJava简单介绍
  1. Just函数
  ```
  just函数code
  ```
  2. Create函数
  ```
  create函数code
  ```
4. RxJava源码分析
  1. 线程实现方法
  2. 回调函数
5. RxJava与retrofit实践
  1. retrofit实现形式
  2. retrofit Factory封装
  3. Dagger2 + Rxjava + Retrofit + mvp最佳实践
