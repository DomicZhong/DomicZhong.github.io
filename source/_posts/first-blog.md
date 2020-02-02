---
title: first blog
date: 2020-02-01 17:13:23
tags: [GIS,young]
categories:
- [Cat1]
- [Cat1-1]
---
+ 标题居中引用
<!-- 标签 方式，要求版本在0.4.5或以上 -->
{% centerquote %}Hexo Markdown Writing Tips{% endcenterquote %}

+ 代码块
{% codeblock lang:javascript %}
	alert("Hello World");
	var myvalue = "Hello World";
{% endcodeblock %}

 
+ tag中英文参考链接
[tag-plugins](https://hexo.io/docs/tag-plugins)
[tag-plugins chinese](http://theme-next.iissnan.com/tag-plugins.html)
[tag-plugins chinese faq](http://theme-next.iissnan.com/faqs.html)

+ markdown 语法参考
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


<!-- + 分隔线

_______
 -->
 
+ 引导带
{% note info %} Content  {% endnote %}
其中，class_name 可以是以下列表中的一个值：
    + default
    + primary
    + success
    + info
    + warning
    + danger
