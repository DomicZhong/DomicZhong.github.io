---
title: First Blog——Markdown 使用技术总结
date: 2020-02-02 20:20:00
tags: [blog,markdown,hexo]
categories:
- [blog]
- [markdown]
---
# Markdown 写作方式总结以及资源分享

首先分享博客创建历程
【20200202 更新】
用了一天终于在2020年2月2日（20200202，是个吉祥的数字）这天把博客搭建好了，域名备案正在进行。
【20200210 更新】
收到[工业和信息化部网站备案系统](http://www.beian.miit.gov.cn) 的邮件，等待了11天的备案终于成功，第一时间把博客挂上去，开心。
ICP, Internet Content Provider 网络内容服务商，即向广大用户综合提供互联网信息业务和增值业务的电信运营商。

<!-- more -->

【20200213 更新】
在ICP备案后还需要到[公网安备案](http://www.beian.gov.cn/portal/index)
公网安备案时需要提供的[阿里云信息](https://developer.aliyun.com/ask/7593?spm=a2c6h.13066354.0.0.5a1433b5zqqjLm)
{% asset_img 备案成功邮件.png ICP备案成功邮件%}

【20200217 更新】
收到公网安备案的短信，备案成功，之前打回去两次，总结一下经验。
首先是公网安备案时需要提供的[阿里云信息](https://developer.aliyun.com/ask/7593?spm=a2c6h.13066354.0.0.5a1433b5zqqjLm)
其次是个人网站备案不能选交互式。

{% asset_img 公网安备案信息截图.png 公网安备案信息%}

{% asset_img 公网安备案编号.png 公网安备案编号%}

## 标题居中引用
<!-- 标签 方式，要求版本在0.4.5或以上 -->
{% centerquote %}Hexo Markdown Writing Tips{% endcenterquote %}


## 代码块
{% codeblock lang:javascript %}
	alert("Hello World");
	var myvalue = "Hello World";
{% endcodeblock %}

 
## tag中英文参考链接
[tag-plugins](https://hexo.io/docs/tag-plugins)
[tag-plugins chinese](http://theme-next.iissnan.com/tag-plugins.html)
[tag-plugins chinese faq](http://theme-next.iissnan.com/faqs.html)

## markdown 语法参考
[markdown W3Cschool](https://www.w3cschool.cn/markdownyfsm/markdownyfsm-odm6256r.html)
[markdown csdn](https://editor.csdn.net/md/)


<!-- 标签 方式，要求版本在0.4.5或以上 -->
<!-- 图片地址、 alt (悬停提示)和 title（标题） 属性-->
[comment]: # ({% fullimage /image-url, alt, title %})

<img src="https://wonderfulengineering.com/wp-content/uploads/2014/07/Landscape-wallpapers-20.jpg"
alt="Click Me"
title = "Landscape"
class="full-image" />


<!-- Asset 引用图片 -->
{% asset_img land.jpg land pic%}
{% asset_link land.jpg %}
{% asset_path land.jpg %}

_______

 
## 引导带
[comment]: # ({% note info %} Content  {% endnote %})
其中，class_name 可以是以下列表中的一个值：
    + default
    + primary
    + success
    + info
    + warning
    + danger


## 音乐设置（见右上角）
<div id="dg" style="z-index: 9999; position: fixed ! important; right: 0px; top: 0px;">
<!-- Simple example (id, server, type)  -->
{% meting "502192384" "netease" "playlist" "mutex:false" "listfolded" "mini" "theme:#ad7a86" %}
</div>


## 表格

项目| Value
---|----
电脑|4199
手机|2120

## 引用
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

## 强调
- 斜体
*single asterisks*
_single asterisks_

- 强调
**single asterisks**
__single asterisks__

- 代码块
`code here`
``code here``



