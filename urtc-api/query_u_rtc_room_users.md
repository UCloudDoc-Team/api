# 查询房间列用户列表信息-QueryURtcRoomUsers

查询房间列用户列表信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|	查询的AppId (不能为空)|**Yes**|
|RoomId|string|查询的房间id(不能为空)|**Yes**|
|StartTime|int|待查询开始时间|**Yes**|
|EndTime|int|待查询结束时间|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode为0时返回succed,不为0返回具体的错误消息提示内容|**Yes**|
|Data|array|用户信息列表（数组元素查看RoomUsersInfo）|**Yes**|

## RoomUsersInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|区域|**Yes**|
|UserId|string|用户ID|**Yes**|
|LastEnterTime|int|最近一次进入房间时间|**Yes**|
|LastLeaveTime|int|最后一次进入房间时间|**Yes**|
|Sdkv|string|sdk版本|**Yes**|
|Device|string|设备名称|**Yes**|
|System|string|系统类型|**Yes**|
|Network|string|网络类型|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryURtcRoomUsers
&AppId=URtc-h4r1txxy
&RoomId=2800
&StartTime=6
&EndTime=3
```

# Response Example
```
{
    "Msg": "dvDadUvN", 
    "Action": "QueryURtcRoomUsersResponse", 
    "Data": [
        {
            "Network": "4g", 
            "Sdkv": "1.4.3", 
            "LastEnterTime": 1570677340, 
            "Region": "长沙", 
            "UserId": "atgPMSIG", 
            "System": "android9arm64-v8a", 
            "LastLeaveTime": 1570677860, 
            "Device": "HUAWEI_DUK-AL20_HUAWEIDUK-AL20"
        }
    ], 
    "RetCode": 0
}
```

