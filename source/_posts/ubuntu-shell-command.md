title: ubuntu 常用命令
date: 2016-01-18 17:01:55
tags: linux命令
---
```bash
#aptitude 命令提供依赖解决方案,降级或升级解决软件依赖,单一软件依赖可用apt-get install 软件名=版本号 -f

#ssh远程登陆
ssh 用户名@ip地址 -p端口 默认22端口

#删除软件
sudo apt-get autoremove 软件名
sudo apt-get autoclean 软件名
dpkg -l |grep ^rc|awk '{print $2}' |tr ["\n"] [" "]|sudo xargs dpkg -P -

#让命令后台运行
nohup npm start &

#查看进程
ps -ef | grep 进程名

#查看某个端口是否被占用详细信息
netstat -ntulp | grep 3000 #查看3000端口详细信息,结果最后是进程号

#结束进程 kill 进程号
```
