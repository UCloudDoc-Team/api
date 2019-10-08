# 创建数据库-CreateCatalogDatabase

用户在数据目录中创建新的数据库

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填写为默认项目|No|
|DatabaseName|string|数据库名称|**Yes**|
|DatabaseDescription|string|数据库描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|DatabaseName|string|数据库名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateCatalogDatabase
&Region=xxx
&ProjectId=OLQZKSlp
&DatabaseName=db9
&DatabaseDescription=xxx
```

# Response Example
```
{
    "Action": "CreateCatalogDatabaseResponse", 
    "Request": "hugoLRSR", 
    "RetCode": 0, 
    "DatabaseName": "db9"
}
```

