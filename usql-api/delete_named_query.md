# 删除命名的SQL查询-DeleteNamedQuery

删除用户已经保存的命名SQL查询

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID， 不填则为默认项目|No|
|NamedQueryId|string|已命名的SQL查询ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|NamedQueryId|string|删除的已保存SQL的ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteNamedQuery
&Region=xxx
&ProjectId=XNYDSKoW
&NamedQueryId=3
```

# Response Example
```
{
    "Action": "DeleteNamedQueryResponse", 
    "Request": "ccfec700-d95d-41ba-9873-5a8bdcb008de", 
    "RetCode": 0, 
    "NamedQueryId": 3
}
```

