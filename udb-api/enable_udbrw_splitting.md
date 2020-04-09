# 启用读写分离功能-EnableUDBRWSplitting

开启DB的读写分离功能

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|MasterDBId|string|DB实例ID（主库）|**Yes**|
|BackupZone|string|备份的可用区。用于创建跨可用区读写分离的一个节点，跨机房的读写分离必须有这个参数|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|MasterDBId|string|DB实例ID（主库）|No|
|RWIP|string|读写分离访问IP|No|

# Request Example
```
https://api.ucloud.cn/?Action=EnableUDBRWSplitting
&Region=cn-zj
&Zone=cn-zj-01
&MasterDBId=DMfqCmki
```

# Response Example
```
{
    "Action": "EnableUDBRWSplittingResponse", 
    "MasterDBId": "WGLtSDkR", 
    "RWIP": "VaaMPTNO", 
    "RetCode": 0
}
```

