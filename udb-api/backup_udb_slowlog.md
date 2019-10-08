# 备份UDB指定时间段的slowlog分析结果-BackupUDBInstanceSlowLog

备份UDB指定时间段的slowlog分析结果

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|DB实例Id,该值可以通过DescribeUDBInstance获取|**Yes**|
|BeginTime|int|过滤条件:起始时间(时间戳)|**Yes**|
|EndTime|int|过滤条件:结束时间(时间戳)|**Yes**|
|BackupName|string|备份文件名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BackupUDBInstanceSlowLog
&Region=cn-bj2
&DBId=udbha-xxxxxx
&BackupName=slow_log_backup
&BeginTime=1432569600
&EndTime=1432588600
```

# Response Example
```
{
    "Action": "BackupUDBInstanceSlowlogResponse", 
    "RetCode": 0
}
```

