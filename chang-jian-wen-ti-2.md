# 常见问题

1.启动报错：java.lang.ClassNotFoundException: com.ruisi.ext.engine.control.ExtContextLoaderListener

回答：

这个类在 ext3-1.4.jar 文件，由于启动jar未被发布到lib目录里，解决方法把ext3-1.4.jar添加到发布源，如下图：

![](/assets/import124.png)

2.标准版mysql还原yunbi\_sys数据库时报 Unknow command '\'' 错，不能还原数。

回答：此问题是数据库编码问题，bi系统数据库编码采用utf8格式，请在还原数据时加上编码设置，如下：

```
mysql -uroot -p --default-character-set=utf8  yunbi_sys<G:\data\yunbi_sys.bak
```



