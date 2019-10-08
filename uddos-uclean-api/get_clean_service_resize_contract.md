# 获取降级任务-GetCleanServiceResizeContract

获取降级任务,不存在降级任务时返回错误

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源id,不允许为空|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ResourceId|string|资源ID|**Yes**|
|BeginTime|string|预约开始调整时间 （时间戳）|**Yes**|
|CleanRegion|string|地域|**Yes**|
|MaxCleanCapacity|int|流量清洗上限防护流量（单位G）5、10、15、20、25|**Yes**|
|ChargeType|string|计费方式（Month:按月，Year:按年）|**Yes**|
|Quantity|int|防护时长（0代表购置月底，年底），仅降级时有效|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetCleanServiceResizeContract
&ResourceId=wMJqpbPN
```

# Response Example
```
{
    "CleanRegion": "hCXSbJlP", 
    "MaxCleanCapacity": 1, 
    "ResourceId": "GebkAmBh", 
    "RetCode": 0, 
    "BeginTime": "hogQIqTB", 
    "ChargeType": "Month", 
    "Action": "GetCleanServiceResizeContractResponse", 
    "Quantity": 3
}
```

