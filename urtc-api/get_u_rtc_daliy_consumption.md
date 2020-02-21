# 获取每日消费时长信息-GetURtcDaliyConsumption

查询消费时长日详情，(根据起始日期和结束日期查询appid的日消费详情，详情包括音频，标清，高清，蓝光，注解默认传入的时间戳参数，后端处理截取到日，查询间隔最大为180天）

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|查询的AppId (不能为空)|**Yes**|
|StartTime|int|开始时间(毫秒时间戳）|**Yes**|
|EndTime|int|结束时间(毫秒时间戳）|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode为0时返回succed,不为0返回具体的错误消息提示内容|**Yes**|
|Data|object|类型参见AppTConsumption，对应的appid每日消费时长详情，包含音频消费时长数组，标清，高清蓝光消费时长数组，数组中具体值的内容参见DailyConsumptionData|**Yes**|

## AppTConsumption
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|AppId（项目id）|No|
|Audio|array|音频消费时长,数组类型，内含每日的具体数据，详情参见DailyConsumptionData |No|
|SdVideo|array|标清消费时长,数组类型，内含每日的具体数据，详情参见DailyConsumptionData |No|
|HdVideo|array|高清消费时长,数组类型，内含每日的具体数据，详情参见DailyConsumptionData |No|
|FhdVideo|array|蓝光消费时长,数组类型，内含每日的具体数据，详情参见DailyConsumptionData |No|

## DailyConsumptionData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|int|时间戳(秒级)|No|
|Value|float|具体的消费数值|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetURtcDaliyConsumption
&AppId=urtc-test
&StartTime=1536529440000
&EndTime=1536615840000
```

# Response Example
```
{
    "Msg": "NFNFfIWS", 
    "Action": "GetURtcDaliyConsumptionResponse", 
    "Data": {
        "FhdVideo": [
            {
                "TimeStamp": 1536624000, 
                "Value": 3333
            }, 
            {
                "TimeStamp": 1536710400, 
                "Value": 2222
            }
        ], 
        "SdVideo": [
            {
                "TimeStamp": 1536624000, 
                "Value": 11111
            }, 
            {
                "TimeStamp": 1536710400, 
                "Value": 33333
            }
        ], 
        "UnitType": 1, 
        "HdVideo": [
            {
                "TimeStamp": 1536624000, 
                "Value": 11111
            }, 
            {
                "TimeStamp": 1536710400, 
                "Value": 33333
            }
        ], 
        "AppId": "urtc-test", 
        "Audio": [
            {
                "TimeStamp": 1536624000, 
                "Value": 12223
            }, 
            {
                "TimeStamp": 1536710400, 
                "Value": 4567
            }
        ]
    }, 
    "RetCode": 0
}
```

