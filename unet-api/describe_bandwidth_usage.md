# 获取带宽用量-DescribeBandwidthUsage

获取带宽用量信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Limit|int|返回数据分页值, 取值范围为 [0,10000000] 之间的整数, 默认为20|No|
|OffSet|int|返回数据偏移量, 默认为0|No|
|EIPIds.n|string|弹性IP的资源Id. 如果为空, 则返回当前 Region中符合条件的所有EIP的带宽用量, n为自然数|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|EIPSet中的元素个数|No|
|EIPSet|array|单个弹性IP的带宽用量详细信息, 详见 UnetBandwidthUsageEIPSet, 如没有弹性IP资源则没有该返回值。|No|

## UnetBandwidthUsageEIPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CurBandwidth|float|最近5分钟带宽用量, 单位Mbps|No|
|EIPId|string|弹性IP资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeBandwidthUsage
&Region=cn-bj2
```

# Response Example
```
{
    "Action": "DescribeBandwidthUsageResponse", 
    " EIPSet": [
        {
            "EIPId": "eip-vuxqym", 
            "CurBandwidth": 4.57763671875e-05
        }, 
        {
            "EIPId": "eip-weiyse", 
            "CurBandwidth": 0
        }
    ], 
    "RetCode": 0
}
```

