# 开启或者关闭UDB从库备份-UpdateUDBInstanceSlaveBackupSwitch

开启或者关闭UDB从库备份

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|MasterDBId|string|主库的Id|**Yes**|
|BackupSwitch|int|从库的备份开关，范围[0,1],0表示从库备份功能关闭,1 表示从库备份开关打开。|**Yes**|
|SlaveDBId|string|从库的Id,如果从库备份开关设定为打开，则必须赋值。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.spark.ucloud.cn/?Action=UpdateUDBInstanceSlaveBackupSwitch 
&Region=cn-bj2
&ProjectId=7                          
&MasterDBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
&SlaveDBId=00cdd68c-c7f5-1252-453c-dfg456d8f0e1
&BackupSwitch=1
```

# Response Example
```
{
    "Action": "UpdateUDBInstanceSlaveBackupSwitchResponse", 
    "RetCode": 0
}
```

