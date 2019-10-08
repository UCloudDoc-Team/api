# 获取 UDPN 价格-GetUDPNPrice

获取 UDPN 价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|No|
|Peer1|string|专线可用区1，支持地域：北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg, 洛杉矶：us-la， 华盛顿：us-ws， 东京：jpn-tky|**Yes**|
|Peer2|string|专线可用区2，支持地域：北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg, 洛杉矶：us-la， 华盛顿：us-ws， 东京：jpn-tky|**Yes**|
|Bandwidth|int|带宽信息|**Yes**|
|ChargeType|string|计费类型|No|
|Quantity|int|购买时长|No|

```
两个端点peer1和peer2之间的线路不一定支持，调用GetUDPNLineList查询支持线路
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PurchaseValue|int|资源有效期 unix 时间戳|**Yes**|
|Price|float|专线价格|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetUDPNPrice
&Region=cn-bj2&Peer1=cn-bj2&Peer2=cn-gd&Bandwidth=2&ChargeType=Month&Quantity=1
```

# Response Example
```
{
    "Action": "GetUDPNPriceResponse", 
    "Price": 200, 
    "PurchaseValue": 1511491209, 
    "RetCode": 0
}
```

