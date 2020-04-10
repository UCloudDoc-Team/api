# 设置读写分离-SetUDBRWSplitting

设置读写分离的模式

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|MasterDBId|string|DB实例ID（master)|**Yes**|
|ReadModel|string|读写分离策略|**Yes**|
|DBIds.n|string|DBIds.0 代表UDB主节点， DBIds.1 到DBIds.n 代表1到N个从节点|**Yes**|
|ReadPercents.n|string|udb主从节点的只读比例。ReadPercents.0代表主节点的只读比例，ReadPercents.1代表从节点1的读写比例， 以此类推|No|
|DelayThreshold|int|时间阙值|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=SetUDBRWSplitting
&Region=cn-zj
&Zone=cn-zj-01
&MasterDBId=KeQskOid
&DelayThreshold=50
&ReadModel=Uniform
&ReadPercentInfo=ocTIdTxW
```

# Response Example
```
{
    "Action": "SetUDBRWSplittingResponse", 
    "RetCode": 0
}
```

