# 更改VPN网关规格-UpdateVPNGateway

更改VPN网关规格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|VPNGatewayId|string|VPN网关的资源ID|**Yes**|
|Grade|string|网关规格。枚举值为: Standard, 标准型; Enhanced, 增强型。|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateVPNGateway
&Region=cn-sh2
&ProjectId=org-XXXXX
&VPNGatewayId=vpngw-XXXX
&Grade=Standard
```

# Response Example
```
{
    "Action": "UpdateVPNGatewayRequestResponse", 
    "RetCode": 0
}
```

