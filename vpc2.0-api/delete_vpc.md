# 删除VPC-DeleteVPC

删除VPC

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|VPCId|string|VPC资源Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteVPC
&Region=cn-sh2
&ProjectId=org-sh2
&VPCId=uvnet-XXXXXX
```

# Response Example
```
{
    "Action": "DeleteVPCResponse", 
    "RetCode": 0
}
```

