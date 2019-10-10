# 删除授权-RemoveUSQLToken

删除用户为USQL访问UCloud其他产品而申请的授权

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|DataSource|string|数据源类型， 如ufile|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Region|string|服务区域|No|
|DataSource|string|数据源类型， 如ufile|No|

# Request Example
```
https://api.ucloud.cn/?Action=RemoveUSQLToken
&Region=cn-bj
&DataSource=ufile
&ProjectId=cpzPYZle
```

# Response Example
```
{
    "Action": "RemoveUSQLTokenResponse", 
    "Region": "pre", 
    "Request": "1a4c13be-e036-4e6d-9e75-7bc3df8349eb", 
    "RetCode": 0, 
    "DataSource": "ufile"
}
```

