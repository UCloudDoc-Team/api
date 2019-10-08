# 获取主备Redis备份下载链接-DescribeURedisBackupURL

获取主备Redis备份下载链接

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|BackupId|int|备份ID|**Yes**|
|RegionFlag|bool|是否是跨机房URedis(默认false)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BackupURL|string|备份文件公网的地址|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeURedisBackupURL
&Region=cn-bj2
&Zone=cn-bj2-03
&BackupId=00f9868c-c7f5-4852-9eac-d200b678f0e1
```

# Response Example
```
{
    "Action": "DescribeURedisBackupURLResponse", 
    "BackupURL": "http://umembackup-5001.cn-bj.ufileos.com/uredis-onb4ha/2222222-8862ba8c-65b0-4691-a8b7-c4ed5f699c64?UCloudPublicKey=ucloududb@ucloud.cn1426152414000604875621&Expires=1495708249&Signature=m/Nh8eEvdF8GvGdYUj/joSf4RJQ=", 
    "RetCode": 0
}
```

