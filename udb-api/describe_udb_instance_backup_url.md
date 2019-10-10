# 获取UDB备份下载地址-DescribeUDBInstanceBackupURL

获取UDB备份下载地址

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|DB实例Id,该值可通过DescribeUDBInstance获取|**Yes**|
|BackupId|int|DB实例备份ID,该值可以通过DescribeUDBBackup获取|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BackupPath|string|DB实例备份文件公网的地址|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBInstanceBackupURL
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
&BackupId=1234
```

# Response Example
```
{
    "Action": "DescribeUDBInstanceBackupURLResponse", 
    "RetCode": 0, 
    "BackupPath": "http://udbbackup.ufile.ucloud.cn/bbasd?UCloudPublicKey=ucloududb@ucloud.cn1426152414000604875621"
}
```

