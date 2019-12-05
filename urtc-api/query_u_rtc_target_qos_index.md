# 查询特定指标-QueryURtcTargetQosIndex

查询特定指标

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|待查询的应用id|**Yes**|
|RoomId|string|待查询的房间名|**Yes**|
|QueryUser|string|待查询的用户名|**Yes**|
|StartTime|int|秒时间戳|**Yes**|
|EndTime|int|秒时间戳|**Yes**|
|IndexType|int|0:common 1:发送方 2.接收方|**Yes**|
|IndexName|int| IndexType为1 1.上行音频码率 2.上行视频码率  3.上行丢包率 4采集音量 5发送延迟 6>帧率IndexType为2 1.下行音频码率 2.下行视频码率  3.下行丢包率 4播放音量 5接收延迟 6>帧率IndexType为0 (1.app的cpu占用率 2.app的内存数  3.设备的cpu占有率)|**Yes**|
|SendUser|string|当QueryUser为接收方时对应的流发送用户的IDQueryUser为发送方时填成一样|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode为0时返回succed,不为0返回具体的错误消息提示内容|**Yes**|
|Data|array|具体返回的值 参加QosItem(time value)|**Yes**|

## QosItem
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|int|时间|**Yes**|
|Value|string|数值|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryURtcTargetQosIndex
&AppId='URtc-h4r1txxy'
&RoomId='2500'
&QueryUser='ssss'
&StartTime=1571196963
&EndTime=1571197963
&IndexType=0
&IndexName=1
&SendUser=HEghJaPl
```

# Response Example
```
{
    "Msg": "Succed", 
    "Action": "QueryURtcTargetQosIndexResponse", 
    "Data": [
        {
            "Value": 100, 
            "Time": 1571196963
        }
    ], 
    "RetCode": 0
}
```

