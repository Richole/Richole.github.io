title: github/gitlab 管理多个ssh key
date: 2016-01-18 15:46:04
tags: git
---
<h3>安装keychain管理ssh</h3>
```bash
sudo apt-get install keychain
```
<h3>生成并添加第一个ssh key</h3>
  第一次使用ssh生成key，默认会在用户~（根目录）下生成 id_rsa, id_rsa.pub 2个文件；所以需要添加多个ssh key时也会生成对应的私钥和公钥。

``` bash
ssh-keygen -t rsa -C "youremail@yourcompany.com"
```
  在Git Bash中执行这条命令一路回车，会在 ~/.ssh/ 目录下生成 id_rsa 和 id_rsa.pub 两个文件，用文本编辑器将 id_rsa_pub 中的内容复制一下粘贴到github(gitlab)上。

<h3>生成并添加第二个ssh key</h3>

``` bash
ssh-keygen -t rsa -C "youremail@yourcompany.com" #注意不要一路回车，要给这个文件起一个名字， 比如叫 id_rsa_github, 所以相应的也会生成一个 id_rsa_github.pub 文件。
```

<h3>添加私钥</h3>

```bash
ssh-add ~/.ssh/id_rsa
ssh-add ~/.ssh/id_rsa_github


如果执行ssh-add时提示"Could not open a connection to your authentication agent"，可以现执行命令：
ssh-agent bash
再执行ssh-add
```

<h3>配置ssh配置文件</h3>
```bash
#如果.ssh目录不存在config文件
touch config
编辑config
# gitlab
Host gitlab
    HostName gitlab.xtremeprog.com
    IdentityFile ~/.ssh/id_rsa_github_120831070

# github
Host github
    HostName github.com
    IdentityFile ~/.ssh/id_rsa
```
<h3>keychain管理ssh</h3>
```bash
keychain ~/.ssh/id_rsa
keychain ~/.ssh/id_rsa_github
# 可以通过 ssh-add -l 来确私钥列表
ssh-add -l

# 可以通过 ssh-add -D 来清空私钥列表
ssh-add -D

#测试github.com
ssh -T git@github.com

#测试gitlab.com
ssh -T git@gitlab.com
```
<h3>ssh远程连接的持久连接配置</h3>
```bash
#修改ssh的配置文件
sudo vim /etc/ssh/ssh_config
#添加两个参数
#保持TCP连接
TCPKeepAlive yes
#每5分钟发送一次心跳包,保持连接
ServerAliveInterval 300
```
