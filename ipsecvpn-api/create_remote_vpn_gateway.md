# 创建客户VPN网关-CreateRemoteVPNGateway

创建客户VPN网关

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|RemoteVPNGatewayName|string|客户VPN网关名称|**Yes**|
|RemoteVPNGatewayAddr|string|客户VPN网关地址|**Yes**|
|Tag|string|业务组名称，默认为 "Default"|No|
|Remark|string|备注，默认为空|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RemoteVPNGatewayId|string|新建客户VPN网关的资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateRemoteVPNGateway
&Region=cn-sh2
&ProjectId=org-XXXXXX
&RemoteVPNGatewayName=test
&RemoteVPNGatewayAddr=1.1.1.1
&Tag=test
&Remark=test
```

# Response Example
```
{
    "Action": "CreateRemoteVPNGatewayResponse", 
    "RemoteVPNGatewayId": "remotevpngw-XXXXX", 
    "RetCode": 0
}
```

