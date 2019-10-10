# 获取备份列表-DescribeUDBBackup

列表UDB实例备份信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Offset|int|分页显示的起始偏移，列表操作则指定|**Yes**|
|Limit|int|分页显示的条目数，列表操作则指定|**Yes**|
|DBId|string|DB实例Id，如果指定，则只获取该db的备份信息 该值可以通过DescribeUDBInstance获取|No|
|BackupType|int|备份类型,取值为0或1，0表示自动，1表示手动|No|
|BeginTime|int|过滤条件:起始时间(Unix时间戳)|No|
|EndTime|int|过滤条件:结束时间(Unix时间戳)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|备份信息 参照UDBBackupSet|No|
|TotalCount|int|满足条件备份总数，如果指定dbid，则是该db备份总数|No|

## UDBBackupSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|备份所在可用区|No|
|BackupId|int|备份id|No|
|BackupName|string|备份名称|No|
|BackupTime|int|备份时间(Unix时间戳)|No|
|BackupSize|int|备份文件大小(字节)|No|
|BackupType|int|备份类型,取值为0或1,0表示自动，1表示手动|No|
|State|string|备份状态 Backuping // 备份中 Success // 备份成功 Failed // 备份失败 Expired // 备份过期|No|
|ErrorInfo|string|备份错误信息|No|
|DBId|string|dbid|No|
|DBName|string|对应的db名称|No|
|BackupZone|string|跨机房高可用备库所在可用区|No|
|BackupEndTime|int|备份完成时间(Unix时间戳)|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBBackup
&Region=cn-bj2
&Offset=0
&Limit=20
```

# Response Example
```
{
    "Action": "DescribeUDBBackupResponse", 
    "TotalCount": 7, 
    "RetCode": 0, 
    "DataSet": [
        {
            "BackupName": "system backup", 
            "BackupTime": 1410894157, 
            "DBId": "c1d1d90d-e039-4483-8cd6-b31614d71817", 
            "BackupSize": 138571, 
            "BackupType": 0, 
            "State": "Backuping", 
            "BackupId": 57214, 
            "DBName": "testtest"
        }, 
        {
            "BackupName": "system backup", 
            "BackupTime": 1412894156, 
            "DBId": "c1d1d90d-e039-4483-8cd6-b31614d71817", 
            "BackupSize": 138571, 
            "BackupType": 0, 
            "State": "Success", 
            "BackupId": 57215, 
            "DBName": "testtest"
        }
    ]
}
```

