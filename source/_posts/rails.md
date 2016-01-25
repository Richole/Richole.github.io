title: rails 环境安装手册
date: 2016-01-11 11:26:10
tags: 环境配置
---

安装 vim, git , npm
sudo apt-get install vim git npm

生成ssh key
ssh-keygen -t rsa -C “dfyu@xtremeprog.com”
cat ~/.ssh/id_rsa.pub #这个是放在gitlab上面的

安装rvm, ruby, rails

#rvm
curl -L get.rvm.io #测试网络
curl -L get.rvm.io | bash -s stable #下载安装
执行 vim ~/.bashofile，在后面添加 [ -f $HOME/.profile ] && source $HOME/.profile

sed -i ‘s!ftp.ruby-lang.org/pub/ruby!ruby.taobao.org/mirrors/ruby!’ $rvm_path/config/db #将rvm的资源地址换到taobao
rvm -v #测试rvm

#ruby
rvm list known #查看有哪些版本可以装
rvm install 2.1.5 #选择某个版本.
rvm use ruby-2.1.5 –default #选择默认版本
ruby -v #查看版本.

更改gem源
gem sources –remove https://rubygems.org/
gem sources –add https://ruby.taobao.org/ #注意是https
gem sources -l #保证只有一个

#rails
gem install rails -v 4.1.1

#安装mysql依赖包
sudo apt-get install libmysqlclient-dev

#bundle
gem install bundle –no-rdoc –no-ri #不装文档

#nvm
git clone https://github.com/creationix/nvm.git ~/.nvm
然后打开~/.bash_profile文件，在其中添加：source ~/.nvm/nvm.sh
nvm install (node的版本号)
然后ln -s 源文件 目标文件 设置软连接到/usr/sbin里
nvm alias default stable
设置nvm默认版本
npm config set strict-ssl false
npm config set registry "http://registry.npmjs.org/" #加快npm下载速度