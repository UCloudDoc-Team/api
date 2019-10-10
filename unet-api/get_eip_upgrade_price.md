# 获取弹性IP带宽改动价格-GetEIPUpgradePrice

获取弹性IP带宽改动价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|EIPId|string|弹性IP的资源ID|**Yes**|
|Bandwidth|int|弹性IP的外网带宽, 单位为Mbps, 范围 [1-800]|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|float|调整带宽后的EIP价格, 单位为"元", 如需退费此处为负值|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetEIPUpgradePrice
&Region=cn-bj2
&Bandwidth=40
&EIPId=eip-XXX
```

# Response Example
```
{
    "Action": "GetEIPUpgradePriceResponse", 
    "Price": 4.6, 
    "Request_uuid": "ccf83d8b-5888-4940-8d18-XXXXX", 
    "PurchaseValue": 1530374400, 
    "RetCode": 0
}
```

