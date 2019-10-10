# 恢复云硬盘-RecoverUDisk

从回收站中恢复云硬盘

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UDiskId|string|云硬盘资源ID|**Yes**|
|ChargeType|string|Year , Month, Dynamic 默认: Dynamic|No|
|Quantity|int|购买时长 默认: 1|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=RecoverUDisk
&Region=cn-sh2
&Zone=cn-sh2-01
&ProjectId=org-xx
&UDiskId=bs-xxx
```

# Response Example
```
{
    "Action": "RecoverUDiskResponse", 
    "RetCode": 0
}
```

