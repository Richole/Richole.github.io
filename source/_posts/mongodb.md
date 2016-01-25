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
<h3>mongodb常用配置命令<h3>
```bash
sudo /etc/init.d/mongodb restart #重启mongodb
sudo vim /etc/mongodb.conf #配置mongodb的配置文件
```
<h3>mongodb常用命令</h3>
```javascript
mongo 数据库名 -u 用户名 -p 密码
db.auth('user','password') #验证数据库用户,需要先use数据库,如果通过admin数据库的验证则获得管理员权限
db.addUser('user','password',true) #为该数据库增加用户,如果为admin数据库,则增加管理员账号,第三个参数是否是只读用户,false则拥有读写权限,如果输入的是已有账号则修改账号信息
db.集合名.remove({}) #删除符合条件的文档
db.集合名.insert(文档) #插入文档
```

