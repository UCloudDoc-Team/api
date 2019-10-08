# 获取数据库-GetCatalogDatabase

获取数据目录下指定名称的数据库详细信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|DatabaseName|string|数据库名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|DatabaseName|string|数据库名称|No|
|DatabaseDescription|string|数据库描述|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetCatalogDatabase
&Region=xxx
&ProjectId=klOgzUzQ
&DatabaseName=db_a

```

# Response Example
```
{
    "Action": "GetCatalogDatabaseResponse", 
    "DatabaseDescription": "xxxxxxxxxxxx", 
    "Request": "a8aaf837-f969-4c98-adf9-22f20d7901f3", 
    "RetCode": 0, 
    "DatabaseName": "db_a"
}
```

