# 修改UPath监控告警项-ModifyUPathTemplate

修改UPath监控告警项

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UPathID|string||No|
|MetricName.n|string||No|
|Threshold.n|int||No|
|AlarmFrequency.n|int||No|
|ContactGroupId.n|int||No|
|Compare.n|string||No|
|AlarmStrategy.n|string||No|
|TriggerCount.n|int||No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyUPathTemplate
&UPathID=wMwpyCnn
&NewProperty=oKFthVxM
```

# Response Example
```
{
    "Action": "ModifyUPathTemplateResponse", 
    "RetCode": 0
}
```

