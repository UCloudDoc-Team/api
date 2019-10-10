# 删除文件系统-RemoveUFSVolume

删除UFS文件系统

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|VolumeId|string|文件系统ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=RemoveUFSVolume
&VolumeId=ufs-xxx
&ProjectId=NahkdNvE
```

# Response Example
```
{
    "Action": "RemoveUFSVolumeResponse", 
    "RetCode": 0
}
```

