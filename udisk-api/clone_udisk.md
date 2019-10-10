# 克隆云硬盘-CloneUDisk

从UDisk创建UDisk克隆

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Name|string|实例名称|**Yes**|
|SourceId|string|克隆父Disk的Id|**Yes**|
|UDataArkMode|string|方舟是否开启，"Yes":开启，"No":关闭；默认为"No"|No|
|Quantity|int|购买时长 默认: 1|No|
|Comment|string|Disk注释|No|
|ChargeType|string|Year , Month, Dynamic，Postpay，Trial 默认: Dynamic|No|
|Tag|string|业务组 默认：Default|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UDiskId|array|创建UDisk Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CloneUDisk
&Region=cn-bj2
&Zone=cn-bj2-04
&SourceId=bs-xxx
&ProjectId=org-xxx
&Name=xxx
&Tag=GtBUxADe
```

# Response Example
```
{
    "Action": "CloneUDiskResponse", 
    "RetCode": 0, 
    "UDiskId": "bs-xxx"
}
```

