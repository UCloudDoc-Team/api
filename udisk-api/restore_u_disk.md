# 从备份恢复数据至UDisk-RestoreUDisk

从备份恢复数据至UDisk

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UDiskId|string|需要恢复的盘id|**Yes**|
|SnapshotId|string|从指定的快照恢复|No|
|SnapshotTime|int|指定从方舟恢复的备份时间点|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=RestoreUDisk
&Region=cn-sh2-01
&Zone=cn-sh2
&UDiskId=bs-xxx
&SnapshotTime=1473646985
```

# Response Example
```
{
    "Action": "RestoreUDiskResponse", 
    "RetCode": 0
}
```

