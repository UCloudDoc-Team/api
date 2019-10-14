# 创建UPath-CreateUPath

创建UPath

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|Name|string|UPath名字|**Yes**|
|LineId|string|选择的线路|**Yes**|
|Bandwidth|int|线路带宽，最小1Mbps,最大800Mbps。每条线路实际可用带宽不同，单条线路购买带宽超过50Mbps请联系产品团队。|**Yes**|
|ChargeType|string|计费模式，默认为Month 按月收费,可选范围['Month','Year','Dynamic']|No|
|Quantity|int|购买周期，ChargeType为Month时，Quantity默认为0代表购买到月底，按时和按年付费该参数必须大于0|No|
|CouponId|string|代金券Id|No|

?> LineId参数范围 从DescribePathXLineConfig接口获取。资源创建后，会开启自动续费，账户剩余额度不足则会产生欠费订单直到资源被回收

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UPathId|string|加速线路实例Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUPath
&Name=test
&LineId=line_cn_afr-nigeria
&Bandwidth=1
&ChargeType=Month
&Quantity=0
&CouponId=
```

# Response Example
```
{
    "PathId": "upath-xxx", 
    "Action": "CreateUPathResponse", 
    "RetCode": 0
}
```

