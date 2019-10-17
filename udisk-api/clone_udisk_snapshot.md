# 克隆快照-CloneUDiskSnapshot

从快照创建UDisk克隆

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Name|string|实例名称|**Yes**|
|SourceId|string|克隆父Snapshot的Id|**Yes**|
|Size|int|购买UDisk大小,单位:GB,范围[1\~8000]。(UDisk大小设定对本地盘快照有效，对云盘快照无效)|No|
|Comment|string|Disk注释|No|
|ChargeType|string|Year , Month, Dynamic，Postpay 默认: Dynamic|No|
|Quantity|int|购买时长 默认: 1|No|
|UDataArkMode|string|是否开启数据方舟 Yes:开启数据方舟 No:关闭数据方舟 默认:No|No|
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
https://api.ucloud.cn/?Action=CloneUDiskSnapshot
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=20
&SourceId=bsSnap-xxx
&Tag=LSaZloNt
```

# Response Example
```
{
    "Action": "CloneUDiskSnapshotResponse", 
    "RetCode": 0, 
    "UDiskId": [
        "bs-xxx"
    ]
}
```

