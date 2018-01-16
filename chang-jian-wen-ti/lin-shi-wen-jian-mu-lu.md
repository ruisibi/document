# 临时文件目录

在最新的睿思BI系统中（V4.0），用户上传的excel,csv,图片等临时文件都放在一个固定的位置。此位置在 ext-config.xml 中配置。

配置如下：

&lt;constant name="upFilePath" value="F:/LicenseServer/file/" /&gt;

对于本地部署睿思BI的客户，请注意修改此路径为本地路径。

