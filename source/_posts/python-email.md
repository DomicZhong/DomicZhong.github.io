---
title: python自动发送qq邮件
categories:
  - - - tool
  - - - python
date: 2020-02-29 16:40:35
tags: [python,email]
---


# 使用python 自动发送qq邮件


[参考教程](https://www.runoob.com/python3/python3-smtp.html)
[参考博客](https://www.cnblogs.com/axinno1/p/8303130.html)


<!-- more -->

目前有个需求就是在阿里云服务器上跑不间断抓取数据的python程序，程序有时会出现bug，因为不可能随时随地都看着程序运行，所以就想到能不能在报错的时候让程序自动发送qq邮件给我，从而及时的通知程序的异常信息。

查了一下相关资料，可以通过SMTP（Simple Mail Transfer Protocol, 即简单邮件传输协议）的方式发送邮件。主要分为3个步骤：

## 获取qq邮箱授权码
首先网页登录qq邮箱，【设置】->【账户】->【POP3/IMAP/SMTP/Exchange/CardDAV/CalDAV服务】，点击开启POP3/SMTP服务,生成授权码。然后按要求发送短信到相关号码，就会得到一串16位的授权码，注意保管好这个授权码，可以多次使用。

{% asset_img SMTP开启及生成授权码.jpg SMTP开启及生成授权码%}

## python发邮件代码
在获得授权码后就可以开始coding了，有个注意点是由于阿里云默认会禁用SMTP的25端口，所以**SMTP的端口需要改为587**，下面把代码分享给大家。

{% codeblock lang:python %}

def SendEmail(mail_string):
    import smtplib
    from email.mime.text import MIMEText
    from email.header import Header
     
    # 第三方 SMTP 服务
    mail_host='smtp.qq.com'  #设置服务器
    mail_user='****'   #用户名, qq号
    mail_pass='****'   # 16位口令
     
     
    sender = '****@qq.com'    #  你的邮箱
    receivers = ['****@qq.com']  # 接收邮件，可设置为你的QQ邮箱或者其他邮箱
     
    message = MIMEText(mail_string, 'plain', 'utf-8') # 邮件正文
    message['From'] = Header("发件人名字", 'utf-8')
    message['To'] =  Header("收件人名字", 'utf-8')
     
    subject = '拥堵抓取程序报错'  # 标题
    message['Subject'] = Header(subject, 'utf-8')

    try:
        smtpObj = smtplib.SMTP() 
        smtpObj.connect(mail_host, 587)    # 587 为 SMTP 端口号
        smtpObj.login(mail_user,mail_pass)
        smtpObj.sendmail(sender, receivers, message.as_string())
        print ("邮件发送成功")
    except Exception as e : #smtplib.SMTPException e:
        print(repr(e))
        print ("Error: 无法发送邮件")
        while True:
            SendEmail(mail_string)
            time.sleep(5)
			
mail_string = "时间:2020-02-29 16:37:10\n成功：40.0,总数40,比率1.0"	
SendEmail(mail_string)

{% endcodeblock %}


## 查看效果
这是发送成功的邮件截图
{% asset_img 邮件截图.png 邮件截图%}



