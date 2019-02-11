---
layout: post
title:  CentOS下搭建Wordpress的坑
categories: [Linux]
tags: [Linux]
---

今天花了几乎一天才把wordpress折腾好，总算是能跑起来了。心累……
<!--more-->

- 安装apache+mysql+php
  - yum install -y httpd php php-fpm mysql mysql-server php-mysql
  - 反射模块，封装了java原生的反射操作，提供简介易用的api，方便使用。

- 启动相应服务

  - service httpd start service mysqld start service php-fpm start

- 配置数据库mysql

  - 简单配置密码 mysqladmin -u root password "XXXXXXXX"

  - 输入 mysql -u root –p 加上之前设置的密码进入数据库

  - 创建一个名为wordpress的数据库 create database wordpress;

- 将wordpress文件夹拷贝到/var/www目录下
  
- 关于外网访问变成localhost的解决方法
  - 找到WordPress数据库中的wp_options字段，修改siteurl和home两条数据的值为“http://主机ip/wordpress”

- 附，常用linux操作

  - 设置httpd，mysqld开机自启 ： chkconfig httpd on   ，    chkconfig mysqld on

  - 关闭linux防火墙 ： 
       - 1，永久性生效 开启：chkconfig iptables on ，关闭：chkconfig iptables off
	   - 2，即时生效，重启后失效 开启：service iptables start ，关闭：service iptables stop
