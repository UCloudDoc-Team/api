# 分配 UDPN 专线-AllocateUDPN

分配一条 UDPN 专线

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Peer1|string|专线可用区1，支持地域：北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg,  洛杉矶：us-la， 华盛顿：us-ws， 东京：jpn-tky|**Yes**|
|Peer2|string|专线可用区2，支持地域：北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg,  洛杉矶：us-la， 华盛顿：us-ws， 东京：jpn-tky|**Yes**|
|Bandwidth|int|带宽|**Yes**|
|ChargeType|string|计费类型，枚举值为： Year，按年付费； Month，按月付费； Dynamic，按需付费|No|
|Quantity|int|计费时长，默认 1|No|
|CouponId|string|代金劵|No|

```
两个端点peer1和peer2之间的线路不一定支持，调用GetUDPNLineList查询支持线路
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UDPNId|string|资源名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=AllocateUDPN
&Peer1=cn-bj2&Peer2=cn-gd&Bandwidth=2&ChargeType=Month&Quantity=1
```

# Response Example
```
{
    "Action": "AllocateUDPNResponse", 
    "UDPNId": "udpn-3hxduk", 
    "RetCode": 0
}
```

