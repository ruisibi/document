# BI系统整合企业微信

1.BI系统整合企业微信后，可以通过微信访问报表，仪表盘等内容，睿思BIV4.5版本开始支持企业微信的整合。

2.首先在BI系统中增加企业微信的相关配置，在application.properties文件中配置。

```
################################微信配置###################
wx.appID=wxe9ded978704a6660
wx.appSecret=
```

3.设置每个用户的微信ID\(OPENDID\)，在权限管理的用户管理中修改，如下图：

![](/assets/importwx.png)

4.在手机报表，仪表盘中点击分享按钮，生成报表URL,并把URL放入企业微信中。用户通过微信可以访问此报表。

![](/assets/importfx.png)

5.请注意在微信后台中设置BI系统的有效地址。

