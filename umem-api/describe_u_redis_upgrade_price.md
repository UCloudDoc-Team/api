# 获取uredis升级价格信息-DescribeURedisUpgradePrice

获取uredis升级价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|Size|int|购买uredis大小,单位:GB,范围是[1-32]|**Yes**|
|GroupId|string|要升级的空间的GroupId,请参考DescribeURedisGroup接口|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|float|扩容差价，单位: 元，保留小数点后两位有效数字|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeURedisUpgradePrice
&Region=cn-bj2
&Zone=cn-bj2-02
&Size=2
&GroupId=uredis-koUgA
```

# Response Example
```
{
    "Action": "DescribeURedisUpgradePriceResponse", 
    "Price": 6273, 
    "RetCode": 0
}
```

