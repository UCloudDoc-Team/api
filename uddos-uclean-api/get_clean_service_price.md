# 获取清洗套餐的价格-GetCleanServicePrice

获取清洗套餐的价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|计费类型（Month:按月，Year:按年）|**Yes**|
|CleanRegion|string|通过GetCleanServiceRegion 维护更新可用的地域列表以应对日益扩张的机房。截止至2019-01-24现网目前可用的列表见枚举：|**Yes**|
|Quantity|int|防护时长（0代表购置月底，年底）|**Yes**|
|MaxCleanCapacity|int|流量清洗上限防护流量（单位G），默认5|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|int|清洗套餐价格|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetCleanServicePrice
&ChargeType=Month
&CleanRegion=TpaukPxG
&MaxCleanCapacity=2
&Quantity=3
```

# Response Example
```
{
    "Action": "GetCleanServicePriceResponse", 
    "Price": 8, 
    "RetCode": 0
}
```

