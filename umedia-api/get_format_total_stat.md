# 获取转封装使用量统计-GetFormatTotalStat

获取转封装使用量统计

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BeginTime|int|查询的开始时间，单位：unix时间戳。如果不传，若没有传结束时间，则为当前时间的前七天。否则为结束时间的前七天。|No|
|EndTime|int|查询的结束时间，单位：unix时间戳。如果不传，若没有传开始时间，则为当前时间，否则为开始时间的后七天。EndTime必须为当前时间往前一个月内，也就是支持一个月内的任务查询。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|StatSet|array|状态列表|No|

## FormatStatInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|统计时间，单位：Unix时间戳|**Yes**|
|FormatTime|int|转封装时长，单位：秒|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetFormatTotalStat
&begintime=1496200000
&endtime= 1496310000
```

# Response Example
```
{
    "Action": "GetFormatTotalStatResponse", 
    "StatSet": [
        {
            "FormatTime": 1200, 
            "Time": 1496204461
        }, 
        {
            "FormatTime": 1200, 
            "Time": 1496304461
        }
    ], 
    "RetCode": 0
}
```

