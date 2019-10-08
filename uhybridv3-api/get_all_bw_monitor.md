# 获取所有监控数据-GetAllBWMonitor

获取所有监控数据

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目id|**Yes**|
|BeginTime|string|开始时间戳|**Yes**|
|EndTime|string|结束时间戳|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息|**Yes**|
|Data|array||**Yes**|

## AllMonitors
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ItemId|int|出／入流量id(出：1002002，入：1002001)|**Yes**|
|Monitors|array|外网监控数据|**Yes**|

## AllBandStats
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BandId|string|带宽id|**Yes**|
|BandNames|string|带宽名|**Yes**|
|Stats|array|监控数据值|**Yes**|

## Stats
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Value|int|数据值(bps)|**Yes**|
|ValueTime|int|数据时间|**Yes**|

# Request Example
```
curl -X POST \
  https://api.ucloud.cn/ \
  -H 'Content-Type: application/json' \
  -d '{
	"Action": "GetAllBWMonitor",

	"Region":"cn-bj2",
	"Zone":"cn-bj2-05",
	
	"BeginTime":"1111",
	"EndTime":"222"
}'
&ProjectId=9
```

# Response Example
```
{
    "Action": "GetAllBWMonitorResponse", 
    "Message": "GetAllBWMonitor ok", 
    "Data": [
        {
            "ItemId": 1002001, 
            "Monitors": []
        }, 
        {
            "ItemId": 1002002, 
            "Monitors": []
        }
    ], 
    "RetCode": 0
}
```

