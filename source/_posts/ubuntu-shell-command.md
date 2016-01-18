title: ubuntu 常用命令
date: 2016-01-18 17:01:55
tags: linux命令
---
<h3>删除软件</h3>
```bash
sudo apt-get autoremove
sudo apt-get autorclean
dpkg -l |grep ^rc|awk '{print $2}' |tr ["\n"] [" "]|sudo xargs dpkg -P -
```
