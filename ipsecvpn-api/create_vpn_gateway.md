# 创建VPN网关-CreateVPNGateway

创建VPN网关

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|VPNGatewayName|string|新建VPN网关名称|**Yes**|
|VPCId|string|新建VPN网关所属VPC的资源ID|**Yes**|
|Grade|string|购买的VPN网关规格，枚举值为: Standard, 标准型; Enhanced, 增强型|**Yes**|
|Remark|string|备注，默认为空|No|
|Tag|string|业务组名称，默认为 "Default"|No|
|Quantity|int|购买时长, 默认: 1|No|
|ChargeType|string|付费方式, 枚举值为: Year, 按年付费; Month, 按月付费；Dynamic, 按需付费(需开启权限)；Trial, 试用(需开启权限)；默认为按月付费|No|
|BusinessId|string|业务组ID|No|
|EIPId|string|若要绑定EIP，在此填上EIP的资源ID|No|
|CouponId|string|代金券ID, 默认不使用|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|VPNGatewayId|string|新建VPN网关的资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateVPNGateway
&Region=cn-sh2
&ProjecId=org-XXXX
&VPNGatewayName=test
&VPCId=uvnet-XXXX
&Bandwidth=8
&ChargeType= Standard
&Tag=test
&Remark=test
```

# Response Example
```
{
    "Action": "CreateVPNGatewayResponse", 
    "RetCode": 0, 
    "VPNGatewayId": "vpngw-XXXX"
}
```

