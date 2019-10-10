# 取消SQL查询-CancelSQLQuery

取消用户提交的SQL查询任务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID， 用户不填则为默认项目|No|
|QueryId|string|SQL查询ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|QueryId|string|被取消的SQL查询ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CancelSQLQuery
&Region=pre
&QueryId= 20180821_120614_00000_a2t8n
&ProjectId=SrqWxCdx
```

# Response Example
```
{
    "Action": "ServiceUnavailableResponse", 
    "QueryId": "20180821_120614_00000_a2t8n", 
    "Request": "bf5c7b0a-12f0-4954-9992-ef53c453aa3c", 
    "RetCode": 0
}
```

