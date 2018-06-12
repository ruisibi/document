# Hadoop导入

系统支持从Hadoop HDFS 上导入数据到BI中。存储在HDFS上的文件是以特殊符号（，）分割的文本文件，系统从指定的HDSF目录下导入数据到BI系统的表中，并可以结合定时任务实现自动导入。

1.点击系统菜单**数据导入** - **Hadoop导入**菜单，系统进入Hadoop 导入页面，如下图：![](/assets/import000.png)2.录入您的HDFS地址信息，点击测试按钮，测试链接是否正常。其中hdfs地址的配置信息在 core-site.xml 文件。

```
<property>
<name>fs.default.name</name>
<value>hdfs://172.30.3.1:9000</value>
</property>
```

3.点击**下一步**后，系统进入导入配置页面，如下图：

![](/assets/import001.png)

