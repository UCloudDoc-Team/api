# 获取命名SQL查询-GetNamedQuery

获取用户保存的SQL查询

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|NamedQueryId|int|已命名查询的Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|QueryName|int|SQL查询名称|No|
|QueryDescription|string|SQL查询描述|No|
|QueryString|string|SQL查询语句|No|
|CreateTime|string|SQL查询保存时间|No|
|NamedQueryId|int|SQL查询ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetNamedQuery
&Region=pre
&NamedQueryId=1
&ProjectId=WiGGBLzY
```

# Response Example
```
{
    "RetCode": 0, 
    "Request": "756275b6-b71c-4844-94b9-1f842b6d7a92", 
    "QueryName": "named_sql", 
    "QueryString": "SELECT * FROM xxxxxx;", 
    "QueryId": 1, 
    "Action": "GetNamedQueryResponse", 
    "QueryDescription": "yyyyyyyyyy", 
    "CreateTime": "2018-08-14T12:55:54.000+0000"
}
```

