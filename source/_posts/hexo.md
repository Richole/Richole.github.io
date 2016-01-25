title: hexo备份整个blog
date: 2016-01-11 11:26:10
tags: [hexo, git]
---
通过hexo新建了一个blog之后，github上面只有blog的静态文件，若要备份整个blog的项目。可通过以下步奏
  1. git clone ... #先拉blog代码

  2. git branch hexo #新建一个hexo分支

  3. git checkout hexo #切换hexo分支

  4. 清除项目文件，并将全部blog文件复制进来

  5. git add -A, git commit -m '...', git push origin hexo:hexo

  6. github设置hexo为默认分支

  7. touch gitignore #新建.gitignore

  8. 设置gitignore
    /node_modules/
    /.deploy_git/
    /public/
    /db.json

  9. 修改hexo免密码登陆
    修改_config.yml repository: github ssh地址
    
  10. hexo clean #重置hexo
提交blog代码有两个步奏

  1. 若要重新部署Blog, hexo g, hexo d #hexo 默认推送代码到master，可在_config.yml更改

  2. 若要备份Blog, git add -A, git commit -m '..', git push origin hexo


