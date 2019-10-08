# 获取UDB的Binlog备份地址-DescribeUDBBinlogBackupURL

获取UDB的Binlog备份地址

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|DBId|string|DB实例Id|**Yes**|
|BackupId|int|DB实例备份ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BackupPath|string|DB实例备份文件的地址|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBBinlogBackupURL
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
&BackupId=1234
```

# Response Example
```
{
    "Action": "DescribeUDBBinlogBackupURLResponse", 
    "RetCode": 0, 
    "BackupPath": "http://udbbackup.ufile.ucloud.cn/bbasd?UCloudPublicKey=ucloududb@ucloud.cn1426152414000604875621&Expires=1426761552&Signature=8MEqKJlwRVLWI1ZvLE/23pveM="
}
```

