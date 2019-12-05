# 查用用户通话时长清单-QueryURtcCallDetail

查用用户通话时长清单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|int|待查询的应用id|**Yes**|
|RoomId|string|	带查询的房间名|**Yes**|
|QueryUser|string|带查询的用户名|**Yes**|
|StartTime|int|查询开始时间（秒级）|**Yes**|
|EndTime|int|查询结束时间（秒级）|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode为0时返回succed,不为0返回具体的错误消息提示内容|**Yes**|
|Data|array|数组元素参见（UserCallInfo）|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryURtcCallDetail
&AppId=URtc-h4r1txxy
&RoomId=222
&QueryUser=200001124
&StartTime=4
&EndTime=1
```

# Response Example
```
{
    "Msg": "Succed", 
    "Action": "QueryURtcCallDetailResponse", 
    "Data": [
        {
            "TimeType": 1, 
            "UserId": "200001124", 
            "Time": 1570686340
        }
    ], 
    "RetCode": 0
}
```

