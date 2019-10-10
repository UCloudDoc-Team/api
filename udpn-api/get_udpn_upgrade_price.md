# 获取升级价格-GetUDPNUpgradePrice

获取专线升级价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UDPNId|string|专线带宽资源 Id|**Yes**|
|Bandwidth|int|带宽|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|float|升级后的价格|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetUDPNUpgradePrice
&UDPNId=udpn-l5m15x
&Bandwidth=6

```

# Response Example
```
{
    "Action": "GetUDPNUpgradePriceResponse", 
    "Price": 226.24, 
    "RetCode": 0
}
```

