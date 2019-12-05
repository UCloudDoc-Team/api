# 查询用户的事件列表-QueryURtcUserEvent

查询用户的事件列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|待查询的应用id|**Yes**|
|RoomId|string|带查询的房间名|**Yes**|
|QueryUser|string|带查询的用户名|**Yes**|
|StartTime|int|待查询开始时间|**Yes**|
|EndTime|int|待查询结束时间|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode为0时返回succed,不为0返回具体的错误消息提示内容|**Yes**|
|Data|array|用户信息列表（数组元素查看UsersEvent）|**Yes**|

## UsersEvent
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UserId|string|用户ID|**Yes**|
|Time|int|时间戳|**Yes**|
|EventType|int|事件类型(1.加入房间，2.离开房间，3.开始推流, 4.结束推流， 5.开始拉流 6.结束拉流 7.打开摄像头 8.关闭摄像头 9.打开麦克风，10.关闭麦克风)|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryURtcUserEvent
&AppId=URtc-h4r1txxy
&RoomId=2800
&QueryUser=android_69dd21e41b1b4f3fa4cc067a02cc04c5
&StartTime=8
&EndTime=1
```

# Response Example
```
{
    "Msg": "succed", 
    "Action": "QueryURtcUserEventResponse", 
    "Data": [
        {
            "EventType": 1, 
            "UserId": "android_69dd21e41b1b4f3fa4cc067a02cc04c5", 
            "Time": 1570677340
        }
    ], 
    "RetCode": 0
}
```

