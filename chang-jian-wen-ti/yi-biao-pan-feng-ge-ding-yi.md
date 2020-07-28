# 仪表盘风格定义

目前bi系统支持9种仪表盘风格（皮肤），用户可以定制自己的仪表盘风格，仪表盘风格配置位置如下图：

![](/assets/importstyle.png)

自定义仪表盘风格：

1.	在 dashboard.js 里增加新的风格代码：

```js
 "<div class=\"form-group\" style=\"margin-right:0px;\"><label class=\"col-sm-4 control-label\">风格：</label><div class=\"col-sm-8\">" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle1' type='radio' value='def' styleTp='def'><label for=\"ybpstyle1\">默认</label></div> " +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle2' type='radio' value='bigscreen' styleTp='bigscreen'><label for=\"ybpstyle2\">风格1</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle3' type='radio' value='bigscreen2' styleTp='bigscreen'><label for=\"ybpstyle3\">风格2</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle4' type='radio' value='bigscreen3' styleTp='bigscreen'><label for=\"ybpstyle4\">风格3</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle5' type='radio' value='bigscreen-t1' styleTp='bigscreen'><label for=\"ybpstyle5\">风格4</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle6' type='radio' value='bigscreen-t2' styleTp='bigscreen'><label for=\"ybpstyle6\">风格5</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle7' type='radio' value='bigscreen-t3' styleTp='bigscreen'><label for=\"ybpstyle7\">风格6</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle9' type='radio' value='bigscreen-n1' styleTp='bigscreen'><label for=\"ybpstyle9\">风格7</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle10' type='radio' value='bigscreen-n2' styleTp='def'><label for=\"ybpstyle10\">风格8</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle11' type='radio' value='bigscreen-n8' styleTp='def'><label for=\"ybpstyle11\">风格9</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle12' type='radio' value='bigscreen-n51' styleTp='def'><label for=\"ybpstyle12\">风格10</label></div>" +
	"<div class=\"radio radio-inline radio-info\"><input name='ybpstyle' id='ybpstyle13' type='radio' value='bigscreen-n36' styleTp='bigscreen'><label for=\"ybpstyle13\">风格11</label></div>" +
"</div></div>"
```

其中关键是设置value 和 styleTp，其中value用来配置仪表盘仪表盘风格的标识，styleTp表示仪表盘组件默认显示风格（def/ bigscreen）两种。 

2.修改src/main/webapp/resource/css/dashboard.css文件，增加新风格的CSS代码，如下：

```css
 /**
新模板 bigscreen-n51
**/
.bg-bigscreen-n51{
	background-color: #e6ede6;
}
.hd-bigscreen-n51 h3{
	color:#fffffd;
	font-size:20px;
	padding-left:15px;
	font-family:Microsoft YaHei;
}
.ybpheader-r-bigscreen-n51 {
	color:#fefefe;
}
.hd-bigscreen-n51 {
	background:url("../bigscreen/head-n30.png") no-repeat center center;
	background-size: 100% 100%;
}
.gp-bigscreen-n51-item {
	background: none;
	color:white !important;
	border: none;
}
.box-bigscreen-n51 {
	border: none;
}
.title-bigscreen-n51 {
	background:url("../bigscreen/panel43.png") no-repeat center center;
	background-size: 100% 100%;
	color: #2a9a2a;
	font-size: 14px;
}
```



