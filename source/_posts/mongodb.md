title: mongodb配置及常用命令
date: 2016-01-20 18:17:01
tags: mongodb
---
<h3>安装</h3>
```bash
deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen #添加软件源
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10 #生成key
sudo apt-get update# 更新软件包
sudo apt-get install mongodb-10gen
```
<h3>mongodb常用命令<h3>
sudo /etc/init.d/mongodb restart #重启mongodb