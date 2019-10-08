# 获取数据表的DDL-GetCatalogTableDDL

获取用户指定名称的数据表的创建DDL

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|DatabaseName|string|数据库名称|**Yes**|
|TableName|string|数据表名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|DatabaseName|string|数据库名称|No|
|TableName|string|数据表名称|No|
|TableDDL|string|数据表结构定义DDL|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetCatalogTableDDL
&Region=xxx
&ProjectId=lCYjZaCF
&DatabaseName=default
&TableName=tbl4
```

# Response Example
```
{
    "RetCode": 0, 
    "Request": "20d3da96-0edd-4429-ba5d-1c5901d6c88b", 
    "TableName": "tbl4", 
    "TableDDL": "CREATE EXTERNAL TABLE `tbl4`(\n`id` string)\nSTORED AS INPUTFORMAT\n'org.apache.hadoop.mapred.TextInputFormat'\nOUTPUTFORMAT\n'org.apache.hadoop.hive.ql.io.HiveIgnoreKeyTextOutputFormat'\nLOCATION\n'ufile://usql/tpc/tpch-s1/nation'\nTBLPROPERTIES (\n'skip.header.line.count'='1',\n'totalSize'='0',\n'delimiter'='|',\n'numFiles'='0',\n'transient_lastDdlTime'='1534840384',\n'classification'='csv')", 
    "DatabaseName": "default", 
    "Action": "GetCatalogTableDDLResponse"
}
```

