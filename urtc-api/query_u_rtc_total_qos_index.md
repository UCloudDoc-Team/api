# 查询总的QOS质量指标(上行总码率，下行总码率，卡顿)-QueryURtcTotalQosIndex

查询总的QOS质量指标(上行总码率，下行总码率，卡顿)

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|待查询的应用id|**Yes**|
|RoomId|string|	带查询的房间名|**Yes**|
|QueryUser|string|带查询的用户名|**Yes**|
|StartTime|int|秒时间戳|**Yes**|
|EndTime|int|秒时间戳|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode为0时返回succed,不为0返回具体的错误消息提示内容|**Yes**|
|Data|object|参见TotalQosIndex|**Yes**|

## TotalQosIndex
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TupBitrate|array|上行总码率|**Yes**|
|TdownBitrate|array|下行总码率|**Yes**|
|TlostFrame|array|卡顿指标|**Yes**|

## QosItem
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|int|时间|**Yes**|
|Value|string|数值|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryURtcTotalQosIndex
&AppId='URtc-h4r1txxy'
&RoomId='8000'
&QueryUser='123'
&StartTime=1571204961
&EndTime=1571205961
```

# Response Example
```
{
    "Msg": "Succeed", 
    "Action": "QueryURtcTotalQosIndexResponse", 
    "Data": {
        "TupBitrate": [
            {
                "Value": 231, 
                "Time": 1571204961
            }, 
            {
                "Value": 222, 
                "Time": 1571204991
            }
        ], 
        "TlostFrame": [
            {
                "Value": 231, 
                "Time": 1571204961
            }, 
            {
                "Value": 222, 
                "Time": 1571204991
            }
        ], 
        "TdownBitrate": [
            {
                "Value": 231, 
                "Time": 1571204961
            }, 
            {
                "Value": 222, 
                "Time": 1571204991
            }
        ]
    }, 
    "RetCode": 0
}
```

