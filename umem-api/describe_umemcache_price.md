# 获取umemcache组价格-DescribeUMemcachePrice

获取umemcache组价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|Size|int|容量大小,单位:GB 取值范围[1-32]|**Yes**|
|ChargeType|string|计费模式，Year， Month， Dynamic，默认: Dynamic 默认: 获取所有计费模式的价格|No|
|Quantity|int|购买umemcache的时长，默认值为1|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|价格列表, 参见 UMemcachePriceSet|No|

## UMemcachePriceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|计费模式，Year, Month, Dynamic|No|
|Price|int|总价格|No|
|OriginalPrice|int|原价|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUMemcachePrice
&Region=cn-north-02
&Size=1   
&ChargeType=Month
&Quantity=1
&ProjectId=org-quk5zs
```

# Response Example
```
{
    "Action": "DescribeUMemcachePriceResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Price": 60, 
            "ChargeType": "Month"
        }
    ]
}
```

