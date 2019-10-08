# 创建快照-CreateUDiskSnapshot

创建snapshot快照

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UDiskId|string|快照的UDisk的Id|**Yes**|
|Name|string|快照名称|**Yes**|
|Quantity|int|购买时长 默认: 1  (已废弃)|No|
|ChargeType|string|Year , Month, Dynamic 默认: Dynamic  (已废弃)|No|
|Comment|string|快照描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SnapshotId|array|快照Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUDiskSnapshot
&Region=cn-bj2
&Zone=cn-bj2-04
&UDiskId=bs-xxx
&Name=test_snapshot
&Comment=test
```

# Response Example
```
{
    "Action": "CreateUDiskSnapshotResponse", 
    "SnapshotId": [
        "bsSnap-xxx"
    ], 
    "RetCode": 0
}
```

