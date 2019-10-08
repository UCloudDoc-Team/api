# 备份UDB指定时间段的errorlog-BackupUDBInstanceErrorLog

备份UDB指定时间段的errorlog

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|DB实例Id,该值可以通过DescribeUDBInstance获取|**Yes**|
|BackupName|string|备份名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BackupUDBInstanceErrorLog
&Region=cn-bj2
&DBId=2bbf9968-2ded-48c5-89c0-4f4d683bdd6c
&BackupName=error_log_backup
```

# Response Example
```
{
    "Action": "BackupUDBInstanceErrorLogResponse", 
    "RetCode": 0
}
```

