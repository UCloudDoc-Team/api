# 添加VPC网段-AddVPCNetwork

添加VPC网段

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|VPCId|string|源VPC短ID|**Yes**|
|Network.n|string|增加网段|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=AddVPCNetwork
&ProjectId=org-XXXXX
&Region=cn-sh2
&VPCId=vnet-XXXXX
&Network.0=10.1.0.0/16
```

# Response Example
```
{
    "Action": "AddVPCNetworkResponse", 
    "RetCode": 0
}
```

