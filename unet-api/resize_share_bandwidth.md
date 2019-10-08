# 调整共享带宽-ResizeShareBandwidth

调整共享带宽的带宽值

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ShareBandwidth|int|带宽值，单位为Mb，范围 [20-5000] (最大值受地域限制)|**Yes**|
|ShareBandwidthId|string|共享带宽的Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ResizeShareBandwidth
&Region=cn-bj2
&ShareBandwidth=100
&ShareBandwidthID=bwshare-fvdr45
```

# Response Example
```
{
    "Action": "ResizeShareBandwidthResponse", 
    "RetCode": 0
}
```

