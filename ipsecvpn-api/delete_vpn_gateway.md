# 删除VPN网关-DeleteVPNGateway

删除VPN网关

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|VPNGatewayId|string|VPN网关的资源ID|**Yes**|
|ReleaseEip|bool|删除VPN时是否一并释放EIP。false，只解绑EIP不删除EIP；true，解绑并释放EIP。默认是false|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteVPNGateway
&Region=cn-sh2
&ProjectId=org-XXXXXX
&VPNGatewayId=vpngw-XXXX
&ReleaseEip=true
```

# Response Example
```
{
    "Action": "DeleteVPNGwResponse", 
    "RetCode": 0
}
```

