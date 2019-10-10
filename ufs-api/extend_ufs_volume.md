# 文件系统扩容-ExtendUFSVolume

文件系统扩容

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|VolumeId|string|文件系统ID|**Yes**|
|Size|int|文件系统大小，单位为GB，最大不超过20T，香港容量型必须为100的整数倍，Size最小为500GB，北京，上海，广州的容量型必须为1024的整数倍，Size最小为1024GB。性能型文件系统Size最小为100GB|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ExtendUFSVolume
&Region=fyiyATYD
&ProjectId=EWzAVWhG
&VolumeId=ufs-xxx
&Size=500
```

# Response Example
```
{
    "Action": "ExtendUFSVolumeResponse", 
    "RetCode": 0
}
```

