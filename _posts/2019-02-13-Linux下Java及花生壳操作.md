---
layout: post
title:  Linux下Java&花生壳DDNS
categories: [Linux]
tags: [Linux]
---

针对Linux下JavaEE环境搭建及DDNS操作
<!--more-->

- 搭建JavaEE环境
  - 拷贝jdk，tomcat到centos相应目录下。

  - 编辑etc/profile文件

  - 添加 
  		- JAVA_HOME=jdk安装目录全路径
  		- export PATH=$JAVA_HOME/bin:$PATH

  - 启动tomcat
  		- 切换到tomcat的bin目录下执行    ./startup.sh

		

- linux下的DDNS操作

  - 用rpm指令安装

  		- rpm -ivh  phddns-3.0-1.x86_64.rpm
  - 输入phddns回车后，可以看到扩展的功能：

  - phddns start（启动）| stop（停止）| status（状态）| restart（重启）|
  
  - phddns reset（重置）

  - phddns version（版本）

 