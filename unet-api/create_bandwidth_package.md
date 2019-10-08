# 创建带宽包-CreateBandwidthPackage

为非共享带宽模式下, 已绑定资源实例的带宽计费弹性IP附加临时带宽包

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Bandwidth|int|带宽大小(单位Mbps), 取值范围[2,800] (最大值受地域限制)|**Yes**|
|EIPId|string|所绑定弹性IP的资源ID|**Yes**|
|TimeRange|int|带宽包有效时长, 取值范围为大于0的整数, 即该带宽包在EnableTime到 EnableTime+TimeRange时间段内生效|**Yes**|
|EnableTime|int|生效时间, 格式为 Unix timestamp, 默认为立即开通|No|
|CouponId|string|代金券ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BandwidthPackageId|string|所创建带宽包的资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateBandwidthPackage
&Region=cn-bj2
&EIPId=eip-vuxqym
&Bandwidth=200
&EnableTime=1430986009
&TimeRange=1
```

# Response Example
```
{
    "Action": "CreateBandwidthPackageResponse", 
    "BandwidthPackageId": "bwpack-rybftq", 
    "RetCode": 0
}
```

