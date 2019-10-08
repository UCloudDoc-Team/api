# 删除VPC互通-DeleteVPCIntercom

删除VPC互通关系

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|源VPC所在地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|源VPC所在项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|VPCId|string|源VPC短ID|**Yes**|
|DstVPCId|string|目的VPC短ID|**Yes**|
|DstRegion|string|目的VPC所在地域，默认为源VPC所在地域|No|
|DstProjectId|string|目的VPC所在项目ID，默认为源VPC所在项目ID|No|

```
删除VPC打通关系
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteVPCIntercom
&Region=cn-sh2
&ProjectId=org-XXX
&VPCId=uvnet-XXX
&Region=cn-sh2
&DstProjectId=org-XXX
&DstVPCId=uvnet-XXX
```

# Response Example
```
{
    "Action": "DeleteVPCIntercomResponse", 
    "RetCode": 0
}
```

