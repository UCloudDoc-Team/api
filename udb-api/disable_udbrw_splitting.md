# 关闭读写分离功能-DisableUDBRWSplitting

关闭DB的读写分离功能

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|MasterDBId|string|DB实例ID（master)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DisableUDBRWSplitting
&Region=cn-zj
&Zone=cn-zj-01
&MasterDBId=eEYotHCo
```

# Response Example
```
{
    "Action": "DisableUDBRWSplittingResponse", 
    "RetCode": 0
}
```

