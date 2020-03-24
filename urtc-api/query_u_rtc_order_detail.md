# 查询房间通话详单-QueryURtcOrderDetail

查询房间通话详单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|AppId|string|AppId|**Yes**|
|RoomId|string|房间ID|**Yes**|
|StartTime|string|起始时间|**Yes**|
|EndTime|string|结束时间|**Yes**|
|Type|string|产品类型（RTC/RECORD）,默认RTC|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20，最大100|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode为0时返回succed,不为0返回具体的错误消息提示内容|**Yes**|
|Data|array|通话详单|**Yes**|
|TotalCount|int|总数|No|

## CallDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RoomId|string|房间ID|No|
|UserId|string|用户ID|No|
|Device|string|设备信息|No|
|Type|string|房间类型|No|
|Role|string|用户角色|No|
|Stats|array|消费时长统计|No|
|JoinTime|int|加入时间|No|
|LeaveTime|int|离开时间|No|

## CallStat
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Profile|string|类型|No|
|Count|int|数值|No|

# Request Example
```
https://api.ucloud.cn/?Action=QueryURtcOrderDetail
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=IxxspcxF
&AppId=GuhyRJFy
&RoomId=oAiTQZhj
&StartTime=RrmweoSS
&EndTime=mRqQbUCe
&Offset=3
&Limit=5
&Type=uvcxDWNN
```

# Response Example
```
{
    "Msg": "oxmHixxX", 
    "Action": "QueryURtcOrderDetailResponse", 
    "Data": [
        {
            "Stats": [
                {
                    "Profile": "tLlHOEKw", 
                    "Count": 1
                }
            ], 
            "RoomId": "AyLAByUb", 
            "UserId": "QtTjzZTK", 
            "LeaveTime": 5, 
            "Role": "PSAtVAyc", 
            "Device": "pPOqiIxB", 
            "JoinTime": 1, 
            "Type": "KgGXsehp"
        }
    ], 
    "RetCode": 0, 
    "TotalCount": 6
}
```

