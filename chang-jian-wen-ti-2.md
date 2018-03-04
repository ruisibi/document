# 常见问题

1.启动报错：java.lang.ClassNotFoundException: com.ruisi.ext.engine.control.ExtContextLoaderListener

回答：

这个类在 ext3-1.4.jar 文件，由于启动jar未被发布到lib目录里，解决方法把ext3-1.4.jar添加到发布源，如下图：

![](/assets/import124.png)



