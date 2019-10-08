# 调整云硬盘-ResizeUDisk

调整UDisk容量

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UDiskId|string|UDisk Id|**Yes**|
|Size|int|调整后大小, 单位:GB, 范围[1~2000],权限位控制可达8000,若需要请申请开通相关权限。|**Yes**|
|MachineType|string|云主机机型（V2.0），枚举值["N", "C", "G", "O", "OM"]。参考[[api:uhost-api:uhost_type|云主机机型说明]]。|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ResizeUDisk
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xx
&UDiskId=bsm-xxx
&Size=20
&MachineType=IxMolmVx
```

# Response Example
```
{
    "Action": "ResizeUDiskResponse", 
    "RetCode": 0
}
```

