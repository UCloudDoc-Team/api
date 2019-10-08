# 获取VPN价格-GetVPNGatewayPrice

获取VPN价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|Grade|string|VPN网关规格。枚举值，包括：标准型：Standard，增强型：Enhanced。|**Yes**|
|ChargeType|string|付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按需付费(需开启权限); 默认为获取三种价格|No|
|Quantity|int|购买时长, 默认: 1|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PriceSet|array|获取的VPN网关价格信息列表，每项参数详见 VPNGatewayPriceSet|No|

## VPNGatewayPriceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|VPN网关付费方式|No|
|Price|float|VPN网关价格, 单位"元"|No|
|PurchaseValue|int|资源有效期, 以Unix Timestamp表示|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetVPNGatewayPrice
&Region=cn-sh2
&ProjectId=org-XXXXXX
&Grade=Standard
&ChargeType=Month
&Quantity=1
```

# Response Example
```
{
    "Action": "GetVPNGatewayPriceResponse", 
    "PriceSet": [
        {
            "Price": 0.19, 
            "PurchaseValue": 1530080647, 
            "ChargeType": "Dynamic"
        }, 
        {
            "Price": 90, 
            "PurchaseValue": 1532669047, 
            "ChargeType": "Month"
        }, 
        {
            "Price": 900, 
            "PurchaseValue": 1561613047, 
            "ChargeType": "Year"
        }
    ], 
    "RetCode": 0
}
```

