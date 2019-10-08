# 获取VPN网关规格改动价格-GetVPNGatewayUpgradePrice

获取VPN网关规格改动价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|VPNGatewayId|string|VPN网关的资源ID|**Yes**|
|Grade|string|更改的VPN网关规格，枚举值为: Standard, 标准型; Enhanced, 增强型。|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|float|调整规格后的VPN网关价格, 单位为"元", 如需退费此处为负值|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetVPNGatewayUpgradePrice
&Region=cn-sh2
&ProjectId=org-XXXXXX
&VPNGatewayId=vpngw-XXXX
&Grade=Standard
```

# Response Example
```
{
    "Action": "GetVPNGatewayUpgradePriceResponse", 
    "Price": 0, 
    "RetCode": 0
}
```

