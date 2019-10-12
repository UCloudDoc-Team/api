# 获取全球加速监控信息-GetPathXMetric

获取全球加速监控信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ResourceId|string|ResourceId，如upath ID  和 uga ID |**Yes**|
|BeginTime|int|查询起始时间，10位长度时间戳|**Yes**|
|EndTime|int|查询结束时间，10位长度时间戳|**Yes**|
|MetricName.n|string|查询监控的指标项。目前仅允许以下四项：NetworkOut:出向带宽，NetworkIn:入向带宽，NetworkOutUsage:出向带宽使用率，NetworkInUsage:入向带宽使用率|**Yes**|
|ResourceType|string|upath:加速线路,uga:加速实例|**Yes**|
|LineId|string|具体线路id，调用DescribePathXLineConfig接口获取线路列表|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|监控数据结果集|No|

## MetricPeriod
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NetworkOut|array|出向带宽|No|
|NetworkIn|array|入向带宽|No|
|NetworkOutUsage|array|出向带宽使用率|No|
|NetworkInUsage|array|入向带宽使用率|No|

## MatricPoint
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Timestamp|int|时间戳 |No|
|Value|int|监控点数值|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetPathXMetric
&ProjectId=org-ejcxxx
&ResourceType=upath
&ResourceId=upath-1boe2u
&BeginTime=1568797253
&EndTime=1568800853
&LineId=line_cn_afr-nigeria
&MetricName.0=NetworkOutUsage
&MetricName.1=NetworkInUsage
```

# Response Example
```
{
    "Action": "GetPathXMetricResponse", 
    "Message": "", 
    "RetCode": 0, 
    "DataSet": {
        "InputRetransmitRate": null, 
        "NetworkOutUsage": [
            {
                "Timestamp": 1568797260, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568797320, 
                "Value": 23
            }, 
            {
                "Timestamp": 1568797380, 
                "Value": 21
            }, 
            {
                "Timestamp": 1568797440, 
                "Value": 20
            }, 
            {
                "Timestamp": 1568797560, 
                "Value": 21
            }, 
            {
                "Timestamp": 1568797620, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568797680, 
                "Value": 16
            }, 
            {
                "Timestamp": 1568797740, 
                "Value": 16
            }, 
            {
                "Timestamp": 1568797800, 
                "Value": 16
            }, 
            {
                "Timestamp": 1568797860, 
                "Value": 16
            }, 
            {
                "Timestamp": 1568797920, 
                "Value": 15
            }, 
            {
                "Timestamp": 1568797980, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568798040, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568798100, 
                "Value": 15
            }, 
            {
                "Timestamp": 1568798160, 
                "Value": 16
            }, 
            {
                "Timestamp": 1568798220, 
                "Value": 17
            }, 
            {
                "Timestamp": 1568798280, 
                "Value": 17
            }, 
            {
                "Timestamp": 1568798340, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568798400, 
                "Value": 15
            }, 
            {
                "Timestamp": 1568798460, 
                "Value": 17
            }, 
            {
                "Timestamp": 1568798520, 
                "Value": 15
            }, 
            {
                "Timestamp": 1568798580, 
                "Value": 16
            }, 
            {
                "Timestamp": 1568798640, 
                "Value": 16
            }, 
            {
                "Timestamp": 1568798700, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568798760, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568798820, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568798880, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568798940, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568799000, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568799060, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568799120, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568799180, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568799240, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568799300, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568799360, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568799420, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568799480, 
                "Value": 15
            }, 
            {
                "Timestamp": 1568799540, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568799600, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568799660, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568799720, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568799780, 
                "Value": 15
            }, 
            {
                "Timestamp": 1568799840, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568799900, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568799960, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568800020, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568800140, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568800200, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568800260, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568800320, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568800380, 
                "Value": 7
            }, 
            {
                "Timestamp": 1568800440, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568800500, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568800560, 
                "Value": 9
            }, 
            {
                "Timestamp": 1568800620, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568800680, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568800740, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568800800, 
                "Value": 11
            }
        ], 
        "NetworkIn": null, 
        "TCPConNum": null, 
        "NetworkOut": null, 
        "OutputRetransmitRate": null, 
        "TCPDelay": null, 
        "NetworkInUsage": [
            {
                "Timestamp": 1568797260, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568797320, 
                "Value": 18
            }, 
            {
                "Timestamp": 1568797380, 
                "Value": 17
            }, 
            {
                "Timestamp": 1568797440, 
                "Value": 17
            }, 
            {
                "Timestamp": 1568797560, 
                "Value": 17
            }, 
            {
                "Timestamp": 1568797620, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568797680, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568797740, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568797800, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568797860, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568797920, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568797980, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568798040, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568798100, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568798160, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568798220, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568798280, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568798340, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568798400, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568798460, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568798520, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568798580, 
                "Value": 14
            }, 
            {
                "Timestamp": 1568798640, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568798700, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568798760, 
                "Value": 13
            }, 
            {
                "Timestamp": 1568798820, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568798880, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568798940, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568799000, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568799060, 
                "Value": 9
            }, 
            {
                "Timestamp": 1568799120, 
                "Value": 9
            }, 
            {
                "Timestamp": 1568799180, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568799240, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568799300, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568799360, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568799420, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568799480, 
                "Value": 12
            }, 
            {
                "Timestamp": 1568799540, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568799600, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568799660, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568799720, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568799780, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568799840, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568799900, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568799960, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568800020, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568800140, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568800200, 
                "Value": 9
            }, 
            {
                "Timestamp": 1568800260, 
                "Value": 10
            }, 
            {
                "Timestamp": 1568800320, 
                "Value": 9
            }, 
            {
                "Timestamp": 1568800380, 
                "Value": 8
            }, 
            {
                "Timestamp": 1568800440, 
                "Value": 8
            }, 
            {
                "Timestamp": 1568800500, 
                "Value": 9
            }, 
            {
                "Timestamp": 1568800560, 
                "Value": 8
            }, 
            {
                "Timestamp": 1568800620, 
                "Value": 9
            }, 
            {
                "Timestamp": 1568800680, 
                "Value": 9
            }, 
            {
                "Timestamp": 1568800740, 
                "Value": 11
            }, 
            {
                "Timestamp": 1568800800, 
                "Value": 9
            }
        ]
    }
}
```

