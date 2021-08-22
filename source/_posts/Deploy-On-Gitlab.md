---
title: Deploy On GitLab
categories:
  - - - blog
  - - - usage
date: 2021-08-22 02:58:30
tags: [blog,usage,hexo,deploy,GitLab]
---

【20200812】
在进行deploy时，GitHub中遇到很多问题，最终不能很好的deploy上去，后面选择了更加友好的GitLab。
[GitLab Blog](https://giser.gitlab.io/)

<!-- more -->

## Deploy在GitLab上的优点
    + 只需一次部署，后面就可以直接在GitLab中添加md文件，可以无需进行本地的更新
    + 部署更加方便，配置稍微简单
    + 支持https

## 使用过的命令

git初始化
``` bash
git init
```

git添加文件
``` bash
git add .
```

git连接远程仓库
``` bash
git remote add origin https://gitlab.com/giser/giser.gitlab.io.git
```


## Hexo中所做的修改

将theme中的".git"文件夹以及".gitignore"文件删除，放置报错

然后更改站点"_config.yml"文件中的url,去掉blog/
``` bash
url: https://giser.gitlab.io/
root: /
```

