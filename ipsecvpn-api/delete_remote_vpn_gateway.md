# 删除客户VPN网关-DeleteRemoteVPNGateway

删除客户VPN网关

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|RemoteVPNGatewayId|string|客户VPN网关的资源ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteRemoteVPNGateway
&Region=cn-sh2
&ProjecId=org-XXXX
&RemoteVPNGatewayId=remotevpngw-XXXX
```

# Response Example
```
{
    "Action": "DeleteRemoteVPNGwResponse", 
    "RetCode": 0
}
```

