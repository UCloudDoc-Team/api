# 列表UDB实例日志备份信息-DescribeUDBLogPackage

列表UDB实例binlog或slowlog或errorlog备份信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Offset|int|分页显示的起始偏移，列表操作则指定|**Yes**|
|Limit|int|分页显示的条目数，列表操作则指定|**Yes**|
|Type|int|需要列出的备份文件类型，每种文件的值如下 2 : BINLOG\_BACKUP 3 : SLOW\_QUERY\_BACKUP 4 : ERRORLOG\_BACKUP|No|
|Types.N|int|Types作为Type的补充，支持多值传入，可以获取多个类型的日志记录，如：Types.0=2&Types.1=3|No|
|DBId|string|DB实例Id，如果指定，则只获取该db的备份信息|No|
|BeginTime|int|过滤条件:起始时间(时间戳)|No|
|EndTime|int|过滤条件:结束时间(时间戳)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|备份信息 参见LogPackageDataSet|No|
|TotalCount|int|备份总数，如果指定dbid，则是该db备份总数|No|

## LogPackageDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BackupId|int|备份id|No|
|BackupName|string|备份名称|No|
|BackupTime|int|备份时间|No|
|BackupSize|int|备份文件大小|No|
|BackupType|int|备份类型，包括2-binlog备份，3-slowlog备份|No|
|State|string|备份状态 Backuping // 备份中 Success // 备份成功 Failed // 备份失败 Expired // 备份过期|No|
|DBId|string|dbid|No|
|DBName|string|对应的db名称|No|
|Zone|string|所在可用区|No|
|BackupZone|string|跨可用区高可用备库所在可用区|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBLogPackage
&Region=cn-bj2
&Zone=cn-bj2-04
&Offset=0
&Limit=20
&Type=2
```

# Response Example
```
{
    "Action": "DescribeUDBLogPackageResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "BackupName": "binlog backup", 
            "BackupTime": 1410894157, 
            "DBId": "c1d1d90d-e039-4483-8cd6-b31614d71817", 
            "BackupSize": 138571, 
            "BackupType": 0, 
            "State": "Backuping", 
            "BackupId": 57214, 
            "DBName": "testtest"
        }
    ]
}
```

