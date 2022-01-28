---
title: 个人介绍子网页部署 Create Personal Portfolio
categories:
  - - - github
  - - - usage
date: 2022-01-28 16:56:49
tags: [github,Portfolio,tool]
---


【20220126】
今天PolyU GDSC (Google Developer Student Club)举办的如何创建和部署个人介绍网页的Workshop很有意思，收获了挺多。这是最终的成果 [My Portfolio Page](https://domiczhong.github.io/portfolio/)!

下面把详细的过程也记录一下

<!-- more -->

## 确定版本
首先确定一下版本

```
node -v
v16.13.2
```

```
Npm -v
8.3.2
```
## 创建工程
确定版本之后，需要创建工程：
- npx create-react-app porfolio-demo
- npm start
- npm install react-bootstrap bootstrap@5.1.3
- npm install react-social-icons
- npm install gh-pages --save-dev

## 编辑工程
工程创建好之后按自己的喜好修改编辑工程，创建个人介绍网页
这边使用的是[React](https://react.docschina.org/docs/react-api.html)+[bootstrap](https://react-bootstrap.github.io/)，可以去React官网寻找相关的教程

[react-social-icons](https://www.npmjs.com/package/react-social-icons)

[buttons](https://react-bootstrap.github.io/components/buttons/)

[grid](https://react-bootstrap.github.io/layout/grid/)


## 同步到github
修改好之后，需要创建Git仓库并链接到远程，然后push
- git init
- git remote add origin https://github.com/DomicZhong/DomicZhong.github.io.git
- git push 

## 部署
每次弄完之后就需要再使用“npm run deploy”命令去部署。
部署完了之后，github上会自动创建一个叫gh-pages的分支，这个是用于github部署的网页。

## 启动github-pages功能
需要在github 库中设置，以启动github-pages功能
如下图
{% asset_img github设置.png github设置%}

## To Do List
1. Improve your website by addin more graphics
2. You can add a form and link it survey monkey or mail-chimp
3. Use wordpress or vix to easily create a website




