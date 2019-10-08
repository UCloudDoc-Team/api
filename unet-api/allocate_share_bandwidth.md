# 开通共享带宽-AllocateShareBandwidth

开通共享带宽

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。|No|
|Name|string|共享带宽名字|**Yes**|
|ChargeType|string|付费方式:Year 按年,Month 按月,Dynamic 按时;|**Yes**|
|ShareBandwidth|int|共享带宽值|**Yes**|
|Quantity|int|购买时长|No|
|ShareBandwidthGuarantee|int|共享带宽保底值(后付费)|No|
|IPVersion|string|共享带宽类型，IPv4或者IPv6，不传默认IPv4|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ShareBandwidthId|string|共享带宽资源Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=AllocateShareBandwidth
&Region=cn-bj2
&ShareBandwidth=20
&ChargeType=Month
&Name=sharebwname
&BwType=XnbjjTdZ
```

# Response Example
```
{
    "Action": "AllocateShareBandwidthResponse", 
    "Request_uuid": "94053674-0160-40f2-8981-XXXXXXX", 
    "RetCode": 0, 
    "ShareBandwidthId": "mdfMzyBm"
}
```

