# 备份云数据库-BackupUDBInstance

备份UDB实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|DB实例Id,该值可以通过DescribeUDBInstance获取|**Yes**|
|BackupName|string|备份名称|**Yes**|
|UseBlacklist|bool|是否使用黑名单备份，默认false|No|
|BackupMethod|string|使用的备份方式。（快照备份即物理备份。注意只有SSD版本的mysql实例支持设置为snapshot）|No|
|Blacklist|string|备份黑名单列表，以 ; 分隔。注意：只有逻辑备份下备份黑名单才生效，快照备份备份黑名单下无效|No|
|ForceBackup|bool|true表示逻辑备份时是使用 --force 参数，false表示不使用 --force 参数。物理备份此参数无效。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BackupUDBInstance    
&Region=cn-bj2
&DBId=udbha-xxxx
&BackupName=master-backup
&BackupMethod=snapshot
&Blacklist=ZScuaauv
&ForceBackup=false
```

# Response Example
```
{
    "Action": "BackupUDBInstanceResponse", 
    "RetCode": 0
}
```

