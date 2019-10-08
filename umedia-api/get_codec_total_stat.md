# 获取转码使用量统计-GetCodecTotalStat

获取转码使用量统计

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|BeginTime|int|查询的开始时间，单位：unix时间戳。如果不传，若没有传结束时间，则为当前时间的前七天。否则为结束时间的前七天。|No|
|EndTime|int|查询的结束时间，单位：unix时间戳。如果不传，若没有传开始时间，则为当前时间，否则为开始时间的后七天。EndTime必须为当前时间往前一个月内，也就是支持一个月内的任务查询。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|StatSet|array|转码使用量数据表|No|

## CodecStatInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|统计时间，单位：Unix时间戳|**Yes**|
|SuperDefinitionTime|int|超高清转码时长，单位：秒|**Yes**|
|HighDefinitionTime|int|超清转码时长，单位：秒|**Yes**|
|MidiumDefinitionTime|int|高清转码时长，单位：秒|**Yes**|
|LowDefinitionTime|int|普清转码时长，单位：秒|**Yes**|
|TotalTime|int|所有清晰度转码时长总和，单位：秒|**Yes**|
|VideoCodec|string|视频的编码类型|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetCodecTotalStat
&begintime=1500220800
&endtime= 1500480000
```

# Response Example
```
{
    "Action": "GetCodecTotalStatResponse", 
    "StatSet": [
        {
            "TotalTime": 0, 
            "MidiumDefinitionTime": 0, 
            "VideoCodec": "h264", 
            "SuperDefinitionTime": 0, 
            "Time": 1500220800, 
            "HighDefinitionTime": 0, 
            "LowDefinitionTime": 0
        }, 
        {
            "TotalTime": 0, 
            "MidiumDefinitionTime": 0, 
            "VideoCodec": "h264", 
            "SuperDefinitionTime": 0, 
            "Time": 1500307200, 
            "HighDefinitionTime": 0, 
            "LowDefinitionTime": 0
        }, 
        {
            "TotalTime": 137, 
            "MidiumDefinitionTime": 0, 
            "VideoCodec": "h264", 
            "SuperDefinitionTime": 0, 
            "Time": 1500393600, 
            "HighDefinitionTime": 0, 
            "LowDefinitionTime": 137
        }, 
        {
            "TotalTime": 137, 
            "MidiumDefinitionTime": 0, 
            "VideoCodec": "h264", 
            "SuperDefinitionTime": 0, 
            "Time": 1500480000, 
            "HighDefinitionTime": 137, 
            "LowDefinitionTime": 0
        }
    ], 
    "RetCode": 0
}
```

