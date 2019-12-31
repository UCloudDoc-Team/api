# 删除Ip-DeleteSecondaryIp

删除ip（用于uk8s使用）

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|Ip|string|ip|**Yes**|
|Mac|string|mac|**Yes**|
|SubnetId|string|子网Id|**Yes**|
|VPCId|string|VPCId|No|
|ObjectId|string|资源Id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteSecondaryIp
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=XhWeOfXN
&ObjectId=RmJfarVf
&Ip=ewgjeWmS
&Mac=JMrfoKTl
&SubnetId=DafEmULF
```

# Response Example
```
{
    "Action": "DeleteSecondaryIpResponse", 
    "RetCode": 0
}
```

