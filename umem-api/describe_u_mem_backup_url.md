# 获取分布式redis 备份下载链接-DescribeUMemBackupURL

获取分布式redis 备份下载链接

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SpaceId|string|资源id|**Yes**|
|BackupId|string|备份Id|**Yes**|
|BlockId|string|分片id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BackupURL|array|备份url，每个分片一个下载URL|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUMemBackupURL
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=lIDfEOmM
&SpaceId=WfTAPwME
&BackupId=HnsnJnXX
&BlockId=NBaSDZeI
```

# Response Example
```
{
    "Action": "DescribeUMemBackupURLResponse", 
    "BackupURL": [
        "GElzOkvy"
    ], 
    "RetCode": 0
}
```

