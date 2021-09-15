---
layout: post
title: CentOS 安装使用 Syncthing
categories: [centos, syncthing]
description: 最近发现服务器的文件越来越多，保存到本地才能让人安心。于是我使用Centos的服务器与Openwrt路由器进行文件同步！
keywords: centos, syncthing
---


最近发现服务器的文件越来越多，保存到本地才能让人安心。
于是我使用Centos的服务器与Openwrt路由器进行文件同步！
Syncthing官网：https://syncthing.net/
安装Syncthing

cd /home
wget https://github.com/syncthing/syncthing/releases/download/v1.18.2/syncthing-linux-amd64-v1.18.2.tar.gz
可以到[GitHub][1]查看最新版本
#解压
tar -zxvf syncthing-linux-amd64-v1.3.3.tar.gz
#进入解压目录将syncthing程序复制到/usr/local/bin目录
cd syncthing-linux-amd64-v1.3.3
cp syncthing /usr/local/bin/

运行

运行一次syncting

#启动syncthing命令
syncthing

然后ctrl+c结束程序
修改配置

sed -i 's/127.0.0.1/0.0.0.0/g' '/root/.config/syncthing/config.xml'

后台运行

nohup syncthing &

日志

在/var/log/syncthing.log
