# 获取umemcache升级价格-DescribeUMemcacheUpgradePrice

获取umemcache升级价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Size|int|购买umemcache大小,单位:GB|**Yes**|
|GroupId|string|需要升级的空间的GroupId,请参考DescribeUMemcacheGroup接口|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|float|价格，单位：元|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUMemcacheUpgradePrice
&Region=cn-north-02
&Size=2
&GroupId=umemcache-abdc2
&ProjectId=org-quk5zs
```

# Response Example
```
{
    "Action": "DescribeUMemcacheUpgradePriceResponse", 
    "Price": 136000, 
    "RetCode": 0
}
```

