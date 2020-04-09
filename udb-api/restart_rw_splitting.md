# 读写分离中间件重启-RestartRWSplitting

读写分离中间件重启，对应docker重启，但是ip不变

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|MasterDBId|string|待关闭读写分离中间键ProxyId|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=RestartRWSplitting
&Region=cn-zj
&Zone=cn-zj-01
&MasterDBId=VLrtcUzD
```

# Response Example
```
{
    "Action": "RestartRWSplittingResponse", 
    "RetCode": 0
}
```

