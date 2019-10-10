# 复制自制镜像-CopyCustomImage

复制自制镜像

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SourceImageId|string|源镜像Id, 参见 DescribeImage|**Yes**|
|TargetProjectId|string|目标项目Id, 参见 GetProjectList|**Yes**|
|TargetRegion|string|目标地域，不跨地域不用填|No|
|TargetImageName|string|目标镜像名称|No|
|TargetImageDescription|string|目标镜像描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TargetImageId|string|目标镜像Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CopyCustomImage
	&Region=cn-bj2
	&SourceImageId=uimage-xxx
 	&TargetProjectId=org-xxx
```

# Response Example
```
{
    "Action": "CopyCustomImageResponse", 
    "TargetImageId": "uimage-xxx", 
    "RetCode": 0
}
```

