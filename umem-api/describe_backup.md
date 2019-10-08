# 查询主备redis备份-DescribeURedisBackup

查询主备redis备份

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Offset|int|分页显示的起始偏移, 默认值为0|No|
|Limit|int|分页显示的条目数, 默认值为10|No|
|GroupId|string|组的ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|用户名下总的备份个数|No|
|DataSet|array|备份列表 参见 URedisBackupSet|No|

## URedisBackupSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BackupId|string|备份ID|No|
|Zone|string|可用区，参见[可用区列表](../summary/regionlist.html)|No|
|GroupId|string|对应的实例ID|No|
|GroupName|string|组名称|No|
|BackupName|string|备份的名称|No|
|BackupTime|int|备份时间 (UNIX时间戳)|No|
|BackupSize|int|备份文件大小, 以字节为单位|No|
|BackupType|string|备份类型: Manual 手动 Auto 自动|No|
|State|string|备份的状态: Backuping 备份中 Success 备份成功 Error 备份失败 Expired 备份过期|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeURedisBackup
&Region=cn-east-01
&Offset=0
&Limit=20
```

# Response Example
```
{
    "Action": "DescribeURedisBackupResponse", 
    "TotalCount": 2, 
    "RetCode": 0, 
    "DataSet": [
        {
            "BackupName": "backup-test", 
            "BackupTime": 1403249482, 
            "BackupSize": 1024, 
            "BackupType": 1, 
            "GroupName": "uredis-one", 
            "State": "Success", 
            "BackupId": "24149c99-4df6-4b5a-99b4-8ab1ca2d7aaa", 
            "GroupId": "uredis-2cwmyb"
        }, 
        {
            "BackupName": "backup-test2", 
            "BackupTime": 1403249482, 
            "BackupSize": 1024, 
            "BackupType": 1, 
            "GroupName": "uredis-two", 
            "State": "Error", 
            "BackupId": "24149c99-4df6-4b5a-99b4-8ab1ca2d7aab", 
            "GroupId": "uredis-0vcq2a"
        }
    ]
}
```

