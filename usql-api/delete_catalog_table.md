# 删除表-DeleteCatalogTable

在数据目录中删除指定数据库中的表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID， 不填则为默认项目|No|
|DatabaseName|string|数据库名称|**Yes**|
|TableName|string|所要删除的表名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|DatabaseName|string|数据库名称|No|
|TableName|string|数据表名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteCatalogTable
&Region=xxx
&ProjectId=gCYWfMgs
&DatabaseName= default
&TableName=tbl7
```

# Response Example
```
{
    "Action": "DeleteCatalogTableResponse", 
    "TableName": "tbl7", 
    "Request": "3f567456-1dfa-43c2-85e7-499b53282869", 
    "RetCode": 0, 
    "DatabaseName": "default"
}
```

