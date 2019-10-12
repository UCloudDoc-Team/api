# 修改UPath监控告警项-ModifyUPathTemplate

修改UPath监控告警项

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UPathId|string|加速线路实例ID|**Yes**|
|MetricName.n|string|告警指标名称, 所有n的个数必须一致。目前仅允许以下四项：UpathNetworkOut:出向带宽，UpathNetworkIn:入向带宽，UpathNetworkOutUsage:出向带宽使用率，UpathNetworkInUsage:入向带宽使用率|No|
|Threshold.n|int|告警阈值，带宽使用率的阈值范围是[50,100]的正整数，带宽告警阈值为1000000的倍数, 如大于2Mbps则告警 阈值应该传 2000000|No|
|AlarmFrequency.n|int|告警探测周期，单位：秒|No|
|ContactGroupId.n|int|告警组id|No|
|Compare.n|string|比较策略，可选 ['GE','LE']  分别代表不小于和不大于|No|
|AlarmStrategy.n|string|收敛策略，可选范围 ['Exponential','Continuous','Once']，分别对应指数递增、连续告警、单次告警|No|
|TriggerCount.n|int|告警触发周期（次数）|No|

```
不同告警指标的 参数单位不一样;参数值后的n可以替换为不同的整数，整数值相同的参数组成一条告警指标
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyUPathTemplate
&ProjectId=org-xxxx
&AlarmStrategy.n=Continuous
&Threshold.n=10000000
&Compare.n=GE
&TriggerCount.n=3
&AlarmFrequency.n=60
&UPathId=upath-xxxx
&MetricName.n=UpathNetworkIn
&ContactGroupId.n=111

```

# Response Example
```
{
    "Action": "ModifyUPathTemplateResponse", 
    "RetCode": 0
}
```

