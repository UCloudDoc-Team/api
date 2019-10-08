# 获取udb实例备份状态-DescribeUDBInstanceBinlogBackupState

获取udb实例备份状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|BackupId|int|备份记录ID|**Yes**|
|BackupZone|string|跨可用区高可用备库所在可用区|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|State|string|备份状态 0 Backuping // 备份中 1 Success // 备份成功 2 Failed // 备份失败 3 Expired // 备份过期|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBInstanceBinlogBackupState
&Region=cn-bj2
&BackupId=8880
```

# Response Example
```
{
    "Action": "DescribeUDBInstanceBinlogBackupStateResponse", 
    "State": "0", 
    "RetCode": 0
}
```

