# 手机报表分享

分享手机报表给其他用户，通过邮件，QQ，微信等多种渠道。主要支持通过邮件分享及直接生成URL两种形式。

1.通过邮件分享

点击**移动BI** - **手机报表管理** 菜单，勾选需要分享的报表，点击**分享**按钮弹出对话框。

![](/assets/import897.png)

录入用户邮件地址，邮件主题，邮件内容等信息，点击**确定**按钮。系统会自动给该用户发邮件，报表以附件形式发送给用户，用户直接下载后可访问。

发送邮件的配置信息在 application.properties 文件中，内容如下。

```
#########################发送邮件配置############################
#发邮件的服务器地址
mail.host=smtp.163.com
#端口
mail.port=25
#发邮件账号
mail.userName=ruisitech@163.com
#发邮件密码
mail.password=
```

2.直接生成报表的URL，再把URL通过QQ，微信等发送给用户。

![](/assets/import865.png)

可以定义报表URL的一些信息，比如是否需要登陆，有效期等内容。点击**确定**按钮生成访问的URL。

