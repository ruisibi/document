# 通过Rest接口导入数据到BI系统

系统默认支持文本/excel/数据库/Hadoop等多种数据源，但其他的数据来源比如web Service，access，其他等，系统未提供完全支持，但系统提供Rest接口，用户可以调用此接口直接向BI系统写数据。

接口地址：http://localhost:8082/rsbi**/etl/dataImpRest.action **, 其中 rsbi 是我的项目名。

请求方式：POST

接口参数：

```js
{
 "tableName":"spb",
 "truncate":false,
 "cols":[
 	{"col":"spm","type":"String", "targetCol":"spm"},
 	{"col":"rq","type":"date", "targetCol":"rq"}
 ],
 "datas":[
 	{"spm":"书本","rq":"2018-07-02 12:45:00"},
 	{"spm":"铅笔","rq":"2018-07-01 10:35:00"}
 ]
}
```

tableName：需要写数据的表名称。

truncate：是否清楚目标表数据，true/false

cols：当前数据和目标表的映射关系。

cols/col： 当前数据集的列

cols/type： 列类型, 支持 String/int/double/Date类型。日期类型格式为：yyyy-MM-dd HH:mm:ss

cols/targetCol：目标表的列

datas：需要写入的数据，数据里的列和cols里对应。







