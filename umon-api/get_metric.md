# 获取监控数据-GetMetric

获取监控数据

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID，不填为默认项目。子账户必须填写项目ID|No|
|ResourceType|string|资源类型|**Yes**|
|MetricName.n|string|指标名称（不同ResourceType对应不同的MetricName）|**Yes**|
|ResourceId|string|资源Id（目前除sharebandwidth可以不传入ResourceId外，其他资源必须传入，sharebandwidth不传入会默认使用获取到的第一个资源Id）|No|
|TimeRange|int|拉取最近多少秒的监控数据，默认1小时，即3600；最大1个月|No|
|BeginTime|int|起始时间unixtimestamp，若传入TimeRange，此项忽略|No|
|EndTime|int|结束时间unixtimestamp，若传入TimeRange，此项忽略；若只传入BeginTime，此项默认为当前时间|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetMetric
&Region=cn-bj2
&Zone=cn-bj2-04
&ResourceType=uhost
&ResourceId=uhost-xxx
&MetricName.1=NetPacketIn
&MetricName.0=NetPacketOut
&BeginTime=1431505992
&EndTime=1431506592
```

# Response Example
```
{
    "Action": "GetMetricResponse", 
    "DataSets": {
        "NetPacketOut": [
            {
                "Timestamp": 1431506100, 
                "Value": 0
            }, 
            {
                "Timestamp": 1431506400, 
                "Value": 0
            }
        ], 
        "NetPacketIn": [
            {
                "Timestamp": 1431506100, 
                "Value": 0
            }, 
            {
                "Timestamp": 1431506400, 
                "Value": 0
            }
        ]
    }, 
    "RetCode": 0
}
```

