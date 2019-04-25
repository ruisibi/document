# 仪表盘模板说明

1.仪表盘的模板数据存在表dashboard\_template中。其中 template\_cfg 为模板的JSON配置， pic 为模板的缩略图名称，缩略图地址为：resource/img/template/。

2.模板JSON说明:

```js
{
	"994e90e3f04ca532c3036b6c8c99a589": {   /*仪表盘组件*/
		"id": "994e90e3f04ca532c3036b6c8c99a589",
		"name": "关键指标",
		"type": "mbox",   /*多指标展现*/
		"kpiJson": [   /*指标*/
			{
				"kpi_id": 1,
				"ydispName": "经营指标1",  /*展现名称*/
				"img": "icon-01.png"   /*展现图片*/
			},
			{
				"kpi_id": 2,
				"ydispName": "经营指标2",
				"img": "icon-02.png"
			},
			{
				"kpi_id": 3,
				"ydispName": "经营指标3",
				"img": "icon-03.png"
			},
			{
				"kpi_id": 4,
				"ydispName": "经营指标4",
				"img": "icon-04.png"
			},
			{
				"kpi_id": 5,
				"ydispName": "经营指标5",
				"img": "icon-05.png"
			},
			{
				"kpi_id": 6,
				"ydispName": "经营指标6",
				"img": "icon-06.png"
			}
		]
	},
	"0cd2c4b2c8a8301ae605088a9cb81531": {  /*仪表盘组件*/
		"id": "0cd2c4b2c8a8301ae605088a9cb81531",
		"name": "业务收入排行Top10",
		"type": "table",   /*表格展现*/
		"mock": "rank",  /*显示排名*/
		"out": "html",  /*输出为自适应大小*/
		"ranking": true,
		"useIn": "dashboard",
		"kpiJson": [  /*表格显示的指标*/
			{
				"kpi_id": 1,
				"kpi_name": "收入",   /*指标名称*/
				"unit": "万元",  /*单位*/
				"alias": "val"  /*别名*/
			}
		],
		"cols": [],
		"rows": [  /*表格行标签*/
			{
				"id": 2,
				"dimdesc": "地域",
				"type": "rank",
				"alias": "key"
			}
		]
	},
	"47823a65aab8fafd3b3ed463103a937d": {  /*仪表盘组件*/
		"id": "47823a65aab8fafd3b3ed463103a937d",
		"name": "业务收入地域分布",  /*组件名称*/
		"type": "chart",   /*组件类型为图*/
		"mock": "area",  /*模拟数据来源*/
		"useIn": "dashboard",
		"chartJson": {
			"type": "map",  /*图形类型为地图*/
			"maparea": "china",  /*中国地图*/
			"typeIndex": "1",
			"dataLabel": true,
			"xcol": {   /*图形横轴为地域*/
				"id": 3,
				"xdispName": "地域",
				"type": "frd",
				"alias": "areaName"
			},
			"ycol": {
				"type": "kpi"
			},
			"showLegend": "true"
		},
		"kpiJson": [  /*图形纵轴指标*/
			{
				"kpi_id": 1,
				"ydispName": "指标",
				"unit": "万元",
				"alias": "val"
			},
			null,
			null
		]
	},
	"9cf372f6ba2cebbccb31ee8fc0b2fdb6": {   /*仪表盘组件*/
		"id": "9cf372f6ba2cebbccb31ee8fc0b2fdb6",
		"name": "销售收入趋势分析",  /*组件名称*/
		"type": "chart",  /*组件类型为图*/
		"mock": "line",
		"useIn": "dashboard",
		"chartJson": {
			"type": "area", /*图形类型为面积图*/
			"typeIndex": "1",
			"xcol": {   /*图形横轴为月份*/
				"id": 1,
				"xdispName": "月份",
				"type": "frd",
				"alias": "key"
			},
			"ycol": {
				"type": "kpi"
			},
			"markerEnabled": "true",  /*禁用描点*/
			"legendpos": "",
			"legendLayout": "",
			"dataLabel": "false",  /*不显示数字标签*/
			"labelType": "nv",
			"showLegend": "false",
			"marginLeft": "40",   /*图形左间距*/
			"marginRight": "30",  /*图形右间距*/
			"spline": true,  /*显示平滑曲线*/
			"splitLine": false,  /*不显示分割线*/
			"makeLine": true /*显示最大，最小，平均线*/
		},
		"kpiJson": [  /*图形显示的指标*/
			{
				"kpi_id": 2,
				"ydispName": "业务收入",
				"alias": "val",
				"unit": "万元"
			}
		],
		"colors": {
			"业务收入": "10"  /*图例颜色索引*/
		}
	},
	"e5392b6478b70668a6d920e1cd356c15": {   /*仪表盘组件*/
		"id": "e5392b6478b70668a6d920e1cd356c15",
		"name": "销售收入构成",  /*组件名称*/
		"type": "chart", /*组件类型为图*/
		"mock": "constitute",
		"useIn": "dashboard",
		"chartJson": {
			"type": "pie",  /*图形类型为饼图*/
			"typeIndex": "2",
			"scol": {
				
			},
			"xcol": {  /*图形横轴为分类*/
				"id": 2,
				"xdispName": "分类",
				"type": "frd",
				"alias": "key"
			},
			"ycol": {
				"type": "kpi"
			},
			"showLegend": "false",   /*不显示图例*/
			"legendpos": "",
			"dataLabel": "true",
			"labelType": "n",
			"innerRing": 30  /*内圈大小*/
		},
		"kpiJson": [   /*图形显示的指标*/
			{
				"kpi_id": 1,
				"ydispName": "销售收入",
				"alias": "val",
				"unit": ""
			}
		]
	},
	"layout": [  /*组件布局器*/
		{
			"id": "0cd2c4b2c8a8301ae605088a9cb81531",
			"col": 1,  /*组件横轴位置*/
			"row": 1,  /*组件纵轴位置*/
			"size_x": 3,  /*组件宽度*/
			"size_y": 4  /*组件高度*/
		},
		{
			"id": "994e90e3f04ca532c3036b6c8c99a589",
			"col": 4,
			"row": 1,
			"size_x": 4,
			"size_y": 4
		},
		{
			"id": "47823a65aab8fafd3b3ed463103a937d",
			"col": 8,
			"row": 1,
			"size_x": 3,
			"size_y": 4
		},
		{
			"id": "9cf372f6ba2cebbccb31ee8fc0b2fdb6",
			"col": 1,
			"row": 5,
			"size_x": 6,
			"size_y": 4
		},
		{
			"id": "e5392b6478b70668a6d920e1cd356c15",
			"col": 7,
			"row": 5,
			"size_x": 4,
			"size_y": 4
		}
	],
	"showFooter": true,  /*仪表盘是否显示页尾*/
	"autoflash": "",
	"style": "bigscreen-t1",/*仪表盘风格*/
	"template": 1/*仪表盘模板ID*/
}
```



