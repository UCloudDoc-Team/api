# 新建VPC互通-CreateVPCIntercom

新建VPC互通关系

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|VPCId|string|源VPC短ID|**Yes**|
|DstVPCId|string|目的VPC短ID|**Yes**|
|DstRegion|string|目的所在地域（如果目的VPC和源VPC不在同一个地域，两个地域需要建立跨域通道，且该字段必选）|No|
|DstProjectId|string|目的项目ID|No|

?> 新建VPC互通关系

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateVPCIntercom
&Region=cn-sh2
&ProjectId=org-XXXXX
&VPCId=uvnet-XXXXX
&DstRegion=cn-sh2
&DstProjectId=org-XXXX
&DstVPCId=uvnet-XXXX
```

# Response Example
```
{
    "Action": "CreateVPCIntercomResponse", 
    "RetCode": 0
}
```

