# 移除硬件隔离组-LeaveIsolationGroup

移除硬件隔离组

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区信息|No|
|ProjectId|string|项目id|No|
|GroupId|string|硬件隔离组id|**Yes**|
|UHostId|string|主机id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UHostId|string|主机id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=LeaveIsolationGroup
&Region=cn-zj
&GroupId=sqDxnHTy
&UHostId=cqCgEwrJ
&Zone=iuFbLPDX
&ProjectId=BoXqQbGF
```

# Response Example
```
{
    "Action": "LeaveIsolationGroupResponse", 
    "GroupId": "ZyzDZUeZ", 
    "RetCode": 0
}
```

