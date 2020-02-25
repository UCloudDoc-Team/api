# 获取umemcache组价格-DescribeUMemcachePrice

获取umemcache组价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Size|int|容量大小,单位:GB 取值范围[1-32]|**Yes**|
|ChargeType|string|计费模式，Year， Month， Dynamic，默认: Dynamic 默认: 获取所有计费模式的价格|No|
|Quantity|int|购买umemcache的时长，默认值为1|No|
|Type|string|空间类型:single(无热备),double(热备)(默认: double)|No|

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
|ListPrice|int|产品列表价|No|
|OriginalPrice|int|原价|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUMemcachePrice
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=1
&ProjectId=NKVlvLHl
&Type=uPFaYIFP
```

# Response Example
```
{
    "Action": "DescribeUMemcachePriceResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Price": 54000, 
            "ListPrice": 54000, 
            "ChargeType": "Year", 
            "OriginalPrice": 54000
        }, 
        {
            "Price": 5400, 
            "ListPrice": 5400, 
            "ChargeType": "Month", 
            "OriginalPrice": 5400
        }, 
        {
            "Price": 11, 
            "ListPrice": 11, 
            "ChargeType": "Dynamic", 
            "OriginalPrice": 11
        }
    ]
}
```

