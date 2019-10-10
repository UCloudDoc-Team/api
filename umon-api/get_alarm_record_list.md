# 获取告警记录列表-GetAlarmRecordList

获取告警记录列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BeginTime|int|开始时间，时间戳|No|
|EndTime|int|结束时间，时间戳（当前仅支持获取时间间隔在31天内的告警记录）|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|告警记录列表|**Yes**|

## AlarmRecord
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源id|**Yes**|
|Region|string|地域编号|No|
|Zone|string|可用区编号|No|
|ResourceType|string|资源类型|**Yes**|
|Name|string|资源名称|**Yes**|
|MetricName|string|指标名称|**Yes**|
|OccurrenceTime|int|告警发生时间|**Yes**|
|RecoveryTime|int|告警恢复时间|**Yes**|
|Recovered|string|是否恢复|**Yes**|
|Threshold|float|阈值|**Yes**|
|Value|float|告警值|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetAlarmRecordList
&ProjectId=ResDQFGv
&BeginTime=923344
&EndTime=5333333
```

# Response Example
```
{
    "Action": "GetAlarmRecordListResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Name": "BXNzRSnO", 
            "ResourceType": "KAInbahB", 
            "ResourceId": "fmLxFLkZ", 
            "OccurrenceTime": 8, 
            "Value": 9.51639, 
            "Recovered": "Yes", 
            "Threshold": 7.97572, 
            "RecoveryTime": 8, 
            "MetricName": "TaRgQmTH"
        }, 
        {
            "Name": "osdailmY", 
            "ResourceType": "WrmwejhS", 
            "ResourceId": "bisLTIWp", 
            "OccurrenceTime": 5, 
            "Value": 5.54988, 
            "Recovered": "Yes", 
            "Threshold": 6.53413, 
            "RecoveryTime": 9, 
            "MetricName": "ASPlEaZc"
        }, 
        {
            "Name": "VAFbFRxD", 
            "ResourceType": "UTROAYRI", 
            "ResourceId": "wCfkteuo", 
            "OccurrenceTime": 2, 
            "Value": 2.27913, 
            "Recovered": "Yes", 
            "Threshold": 8.72818, 
            "RecoveryTime": 8, 
            "MetricName": "KgGCfbqp"
        }, 
        {
            "Name": "XaHhdZLW", 
            "ResourceType": "mdedMlZD", 
            "ResourceId": "QVQMVclb", 
            "OccurrenceTime": 1, 
            "Value": 2.43968, 
            "Recovered": "Yes", 
            "Threshold": 9.22554, 
            "RecoveryTime": 3, 
            "MetricName": "mWQZYFzM"
        }, 
        {
            "Name": "PvSNXQpZ", 
            "ResourceType": "JgCsxfqS", 
            "ResourceId": "JeHDBIwa", 
            "OccurrenceTime": 1, 
            "Value": 4.74256, 
            "Recovered": "Yes", 
            "Threshold": 7.17721, 
            "RecoveryTime": 3, 
            "MetricName": "uqQHIXVE"
        }, 
        {
            "Name": "CMzuWovm", 
            "ResourceType": "WJOMSayg", 
            "ResourceId": "eUISGdGS", 
            "OccurrenceTime": 8, 
            "Value": 1.73251, 
            "Recovered": "Yes", 
            "Threshold": 6.57864, 
            "RecoveryTime": 1, 
            "MetricName": "uSWEzuJi"
        }, 
        {
            "Name": "oEeBdwco", 
            "ResourceType": "gEYdhrGf", 
            "ResourceId": "WdXpvtrI", 
            "OccurrenceTime": 6, 
            "Value": 9.83791, 
            "Recovered": "Yes", 
            "Threshold": 1.52272, 
            "RecoveryTime": 5, 
            "MetricName": "zSIYVqgD"
        }, 
        {
            "Name": "XvyLDfzY", 
            "ResourceType": "JXrsqQwP", 
            "ResourceId": "dZfxKNkY", 
            "OccurrenceTime": 8, 
            "Value": 3.97248, 
            "Recovered": "Yes", 
            "Threshold": 4.31349, 
            "RecoveryTime": 2, 
            "MetricName": "QVYNTUed"
        }, 
        {
            "Name": "ZaEOZbgh", 
            "ResourceType": "LEfmyHmQ", 
            "ResourceId": "ojuzjqkF", 
            "OccurrenceTime": 6, 
            "Value": 4.54875, 
            "Recovered": "Yes", 
            "Threshold": 1.35466, 
            "RecoveryTime": 8, 
            "MetricName": "sndStIsR"
        }, 
        {
            "Name": "tNpywJsP", 
            "ResourceType": "xTnHtABc", 
            "ResourceId": "WjPSUvSp", 
            "OccurrenceTime": 5, 
            "Value": 3.37471, 
            "Recovered": "Yes", 
            "Threshold": 1.33729, 
            "RecoveryTime": 8, 
            "MetricName": "RKOTCDPi"
        }
    ]
}
```

