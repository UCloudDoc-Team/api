# 获取弹性IP价格-GetEIPPrice

获取弹性IP价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|OperatorName|string|弹性IP的线路如下: 国际: International BGP: Bgp 各地域允许的线路参数如下: cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International kr-seoul:International us-ws:International ge-fra:International sg:International tw-kh:International.其他海外线路均为 International,泉州为移动单线cn-qz:ChinaMobile|**Yes**|
|Bandwidth|int|弹性IP的外网带宽, 单位为Mbps, 范围 [0-800]|**Yes**|
|ChargeType|string|付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按时付费; 默认为获取三种价格|No|
|PayMode|string|弹性IP计费方式r. 枚举值为: Traffic, 流量计费; Bandwidth, 带宽计费; "ShareBandwidth",共享带宽模式. 默认为Bandwidth|No|
|Quantity|int|购买时长。默认: 1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传0，代表了购买至月末|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PriceSet|array|弹性IP价格详情 详情见 EIPPriceDetailSet|No|

## EIPPriceDetailSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|弹性IP付费方式|No|
|Price|float|购买弹性IP的实际价格, 单位"元"|No|
|OriginalPrice|float|弹性IP的原价，单位“元”|No|
|PurchaseValue|int|资源有效期, 以Unix Timestamp表示|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetEIPPrice
&Region=cn-bj2
&OperatorName=Bgp
&Bandwidth=4
&ChargeType=Month
&PayMode=Traffic
&Quantity=2
```

# Response Example
```
{
    "Action": "GetEIPPriceResponse", 
    "PriceSet": [
        {
            "Price": 0.1, 
            "PurchaseValue": 1529900854, 
            "ChargeType": "Dynamic"
        }, 
        {
            "Price": 50, 
            "PurchaseValue": 1532489254, 
            "ChargeType": "Month"
        }, 
        {
            "Price": 500, 
            "PurchaseValue": 1561433254, 
            "ChargeType": "Year"
        }
    ], 
    "Request_uuid": "b2f6d562-4a22-428b-b88c-XXXXXX", 
    "RetCode": 0
}
```

