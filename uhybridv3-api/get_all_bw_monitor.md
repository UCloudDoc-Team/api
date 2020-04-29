# 获取所有监控数据-GetAllBWMonitor

获取所有监控数据

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目id|**Yes**|
|BeginTime|string|开始时间戳|**Yes**|
|EndTime|string|结束时间戳|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息|**Yes**|
|Data|array|返回数据|**Yes**|

## Allmonitors
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ItemId|int|监控id|**Yes**|
|Allmonitors|array|监控数据|**Yes**|

## AllmonitorsData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BandId|int|带宽id|No|
|BandName|string|带宽名称|No|
|Stats|array|带宽监控数据|No|

## Stats
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ValueTime|int|时间戳|No|
|Value|int|流量值|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetAllBWMonitor
&Region=ADcLBtAz
&Zone=ICrhStMV
&ProjectId=AflZXzes
&BeginTime=ebjWLqyH
&EndTime=VSMqvpvm
```

# Response Example
```
{
    "Action": "GetAllBWMonitorResponse", 
    "Message": "bIGVEyqT", 
    "Data": [
        {
            "ItemId": 5, 
            "Allmonitors": [
                {
                    "BandId": 7, 
                    "Stats": [
                        {
                            "ValueTime": 2, 
                            "Value": 5
                        }
                    ], 
                    "BandName": "sfvqYSxu"
                }
            ]
        }
    ], 
    "RetCode": 0
}
```

