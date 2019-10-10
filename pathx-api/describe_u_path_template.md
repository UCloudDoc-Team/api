# 查询UPath的监控模板-DescribeUPathTemplate

查询UPath的监控模板

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|UPathId|string|加速线路ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|监控模板详情|**Yes**|

## AlarmRuler
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AlarmStrategy|string|收敛策略，可选范围 ['Exponential','Continuous','Once']，分别对应指数递增、连续告警、单次告警|**Yes**|
|AlarmFrequency|int|告警探测周期，单位秒|**Yes**|
|Compare|string|比较策略，可选 ['GE','LE']  分别代表不小于和不大于|**Yes**|
|ContactGroupId|int|联系组ID|**Yes**|
|MetricName|string|告警指标名称, 所有n的个数必须一致。目前仅允许以下四项：UpathNetworkOut:出向带宽，UpathNetworkIn:入向带宽，UpathNetworkOutUsage:出向带宽使用率，UpathNetworkInUsage:入向带宽使用率|**Yes**|
|Threshold|int|告警阈值，带宽使用率的阈值范围是[50,100]的正整数，带宽告警阈值为1000000的倍数, 如大于2Mbps则告警 阈值应该传 2000000|**Yes**|
|TriggerCount|int|告警触发周期（次数）|**Yes**|
|AlarmTemplateRuleId|string|告警模板策略ID|**Yes**|
|ResourceType|string|资源类型|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUPathTemplate
&UPathId=LhPjtUak
```

# Response Example
```
{
    "Action": "DescribeUPathTemplateResponse", 
    "RetCode": 0
}
```

