# 删除快照-DeleteUDiskSnapshot

删除Snapshot

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|SnapshotId|string|快照Id(填写后不能填写UDisk Id)|No|
|UDiskId|string|UDisk Id,删除该盘所创建出来的所有快照(填写后不能填写SnapshotId)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUDiskSnapshot
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&SnapshotId=bsSnap-xxx
```

# Response Example
```
{
    "Action": "DeleteUDiskSnapshotResponse", 
    "RetCode": 0
}
```

