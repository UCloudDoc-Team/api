# 获取专线线路列表-GetUDPNLineList

获取当前支持的专线线路列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|

?> 两个端点peer1和peer2之间的线路不一定支持，调用GetUDPNLineList查询支持线路

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|DataSet中的元素个数|**Yes**|
|DataSet|array|当前支持的专线线路详细信息，详见UDPNLineSet|**Yes**|

## UDPNLineSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|LocalRegion|string|支持UDPN的地域之一，北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg, 华盛顿：us-ws, 洛杉矶：us-la， 东京：jpn-tky|**Yes**|
|RemoteRegion|string|支持UDPN的地域之一，北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg, 华盛顿：us-ws, 洛杉矶：us-la， 东京：jpn-tky|**Yes**|
|BandwidthUpperLimit|int|线路带宽上限,单位 M|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetUDPNLineList
&公共参数＝
```

# Response Example
```
{
    "Action": "GetUDPNLineListResponse", 
    "TotalCount": 3, 
    "RetCode": 0, 
    "DataSet": [
        {
            "LocalRegion": "cn-bj2", 
            "RemoteRegion": "cn-gd"
        }, 
        {
            "LocalRegion": "cn-gd", 
            "RemoteRegion": "hk"
        }, 
        {
            "LocalRegion": "cn-bj2", 
            "RemoteRegion": "cn-sh2"
        }
    ]
}
```

