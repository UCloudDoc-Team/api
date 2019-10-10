# 获取文件系统列表-DescribeUFSVolume2

获取文件系统列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|VolumeId|string|文件系统ID|No|
|Offset|int|文件列表起始|No|
|Limit|int|文件列表长度|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|文件系统总数|**Yes**|
|DataSet|array|文件系统详细信息列表|**Yes**|

## UFSVolumeInfo2
|Parameter name|Type|Description|Required|
|---|---|---|---|
|VolumeName|string|文件系统名称|**Yes**|
|VolumeId|string|文件系统ID|**Yes**|
|TotalMountPointNum|int|当前文件系统已创建的挂载点数目|**Yes**|
|MaxMountPointNum|int|文件系统允许创建的最大挂载点数目|**Yes**|
|StorageType|string|文件系统存储类型，枚举值，Basic表示容量型，Advanced表示性能型|**Yes**|
|ProtocolType|string|文件系统协议，枚举值，NFSv3表示NFS V3协议，NFSv4表示NFS V4协议|**Yes**|
|Remark|string|文件系统备注信息|No|
|Tag|string|文件系统所属业务组|No|
|CreateTime|int|文件系统创建时间（unix时间戳）|No|
|ExpiredTime|int|文件系统过期时间（unix时间戳）|No|
|Size|int|文件系统大小，单位GB|No|
|UsedSize|int|文件系统当前使用容量，单位GB|No|
|IsExpired|string|是否过期|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUFSVolume2
&Region=cn-zj
&ProjectId=DJpEkpgc
&VolumeId=lhwAtBELNnFFCCtnAZauZUyulVgLTOpIBFF
&Offset=9
&Limit=501
```

# Response Example
```
{
    "Action": "DescribeUFSVolume2Response", 
    "TotalCount": 3, 
    "RetCode": 0, 
    "DataSet": [
        {
            "ExpiredTime": 2, 
            "Remark": "PQJgSJOQ", 
            "MaxMountPointNum": 5, 
            "StorageType": "Advanced", 
            "VolumeName": "qoXVyiHKLrARIxnISVeCmWRTxNCRqkLzfUR", 
            "UsedSize": 1, 
            "VolumeId": "BCUKqVILayBIohkHvMFJcXAukkUgqZMflxt", 
            "ProtocolType": "NFSv4", 
            "Tag": "wVoXCOhQ", 
            "TotalMountPointNum": 1, 
            "IsExpired": "Yes", 
            "CreateTime": 8, 
            "Size": 9
        }, 
        {
            "ExpiredTime": 4, 
            "Remark": "GXBqIxLc", 
            "MaxMountPointNum": 5, 
            "StorageType": "Advanced", 
            "VolumeName": "pYuTTcTGCFkHYOvfgkMVygwakxSnUPQdcEY", 
            "UsedSize": 1, 
            "VolumeId": "ZxaoxhfYQpkFkQWbHCNEDgBeFjBUcOuRuMH", 
            "ProtocolType": "NFSv4", 
            "Tag": "sxtcHxsh", 
            "TotalMountPointNum": 1, 
            "IsExpired": "Yes", 
            "CreateTime": 2, 
            "Size": 9
        }, 
        {
            "ExpiredTime": 8, 
            "Remark": "SYHlTMuO", 
            "MaxMountPointNum": 5, 
            "StorageType": "Advanced", 
            "VolumeName": "LCtDHYigQPztASQNomZHEJliBWpEYgjWNrc", 
            "UsedSize": 1, 
            "VolumeId": "AUFUveZpdYaXsFzzHsBhjNsKyweRXxDxfFh", 
            "ProtocolType": "NFSv4", 
            "Tag": "XJUPznAp", 
            "TotalMountPointNum": 1, 
            "IsExpired": "Yes", 
            "CreateTime": 8, 
            "Size": 5
        }
    ]
}
```

