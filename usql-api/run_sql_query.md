# 运行SQL查询-RunSQLQuery

运行用户编辑的SQL查询

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|DatabaseName|string|数据库名称|**Yes**|
|QueryString|string|SQL查询语句|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|QueryId|string|新建的SQL查询任务的ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=RunSQLQuery
&Region=cn-xxx
&DatabaseName=default
&QueryString=SELECT * FROM nation3 LIMIT 10
&ProjectId=jDsRXind
```

# Response Example
```
{
    "Action": "RunSQLQueryResponse", 
    "QueryId": "20180913_082139_00000_22dwf", 
    "Request": "Qmeoquzn", 
    "RetCode": 0
}
```

