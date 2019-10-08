# 关闭共享带宽-ReleaseShareBandwidth

关闭共享带宽

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ShareBandwidthId|string|共享带宽ID|**Yes**|
|EIPBandwidth|int|关闭共享带宽后，各EIP恢复为的带宽值|**Yes**|
|PayMode|string|Bandwidth 带宽计费, Traffic 转流量计费|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ReleaseShareBandwidth
&Region=cn-bj2
&ShareBandwidthId=bwshare-fvdr45
&EIPBandwidth=2
```

# Response Example
```
{
    "Action": "ReleaseShareBandwidthResponse", 
    "RetCode": 0
}
```

