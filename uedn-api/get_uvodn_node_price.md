# 获取节点价格-GetUvodnNodePrice

获取节点价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IdcId|string|机房Id|**Yes**|
|NodeCount|int|节点数量，默认1|No|
|CpuCore|int|CPU核数|No|
|MemSize|int|内存大小，单位GB|No|
|SysDiskSize|int|系统盘大小，单位GB|No|
|DiskSize|int|数据盘大小，单位GB|No|
|NetLimit|int|网络带宽限速，单位Mbs|No|
|ChargeType|int|付费方式，1按时，2按月，3按年，默认2|No|
|ChargeQuantity|int|月数或者年数，0计费到月底， 默认0|No|
|ProductType|string|产品类型：normal（标准型），hf（高频型），默认normal|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|NodePrice|float|节点价格|No|
|IpPrice|string|Ip和带宽价格|No|

# Request Example
```
http://api.spark.ucloud.cn/?Action= GetUvodnNodePrice
& CpuCore=1& MemSize=2& DiskSize=2& IpCount=1& ChargeType=1& ChargeQuantity=1& Count=1
&NodeCount=8
&CpuCore=3
&MemSize=8
&SysDiskSize=3
&DiskSize=3
&NetLimit=7
&ChargeType=3
&ChargeQuantity=2
&ProductType=etrzrMbV
```

# Response Example
```
{
    "Action": "GetUvodnNodePriceResponse", 
    "Price": 82989, 
    "RetCode": 0, 
    "IpPrice": "ijOBFcwN"
}
```

