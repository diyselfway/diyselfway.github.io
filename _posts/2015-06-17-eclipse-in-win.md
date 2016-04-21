---
layout:     post
title:      "在eclipse中配置Java开发环境"
subtitle:   "磨刀不误砍柴工"
date:       2015-06-17 00:00:00
author:     "Julian"
header-img: "img/post-bg-hello.jpg"
published: true
tags: 工具 Java
---

* toc
{:toc}

### 下载

eclipse 官网下载：[https://eclipse.org/downloads/](https://eclipse.org/downloads/)
Java SDK 下载：[官网下载](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

### 配置环境

下载好 Java SDK 后安装好，我的路径是 D:\Java\jdk1.8.0_51
打开我的电脑--属性--高级--环境变量
新建系统变量 JAVA_HOME 和 CLASSPATH ，分别配置如下：

>变量名：JAVA_HOME 
>变量值：D:\Java\jdk1.8.0_51

>变量名：CLASSPATH 
>变量值：;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;

继续添加Path路径
选择“系统变量”中变量名为“Path”的环境变量，双击该变量，把JDK安装路径中bin目录的绝对路径，添加到Path变量的值中，并使用半角的分号和已有的路径进行分隔。如下配置：

>变量名：Path 
>变量值：%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;

### 安装eclipse

现在可以来安装我们下载好的eclips，安装完之后启动就能看到支持java开发了。
eclip内置了一个jre环境，我们也可以打开windows-prefence配置自己的jre。