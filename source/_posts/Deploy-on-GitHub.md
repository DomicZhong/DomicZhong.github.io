---
layout: w
title: Deploy on GitHub
date: 2021-08-22 15:46:00
tags: [blog,usage,hexo,deploy,GitHub]
---

【20200822】
今天终于将网站Deploy到Github上了，下面记录一下过程
[GitHub Blog](https://domiczhong.github.io/)

<!-- more -->

## Deploy在GitHub上的优点,与GitLab一致
    + 只需一次部署，后面就可以直接在GitHub中添加md文件，可以无需进行本地的更新
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
git remote add origin https://github.com/DomicZhong/DomicZhong.github.io.git
```

将branch切换到source中，当source更新后自动会在主页显示
git切换Branch
``` bash
git switch source
```

自动部署的原理是来源于添加了yml配置文件
``` bash
.github/workflows/pages.yml
name: Pages

on:
  push:
    branches:
      - source  # default branch

jobs:
  pages:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Use Node.js 12.x
        uses: actions/setup-node@v1
        with:
          node-version: '12.x'
      - name: Cache NPM dependencies
        uses: actions/cache@v2
        with:
          path: node_modules
          key: ${{ runner.OS }}-npm-cache
          restore-keys: |
            ${{ runner.OS }}-npm-cache
      - name: Install Dependencies
        run: npm install
      - name: Build
        run: npm run build
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
          publish_branch: master  # deploying branch
```


## Hexo中所做的修改

在GitLab的基础上，进行如下更新
删除next中“languages”文件夹内的md文件，不然会报错



