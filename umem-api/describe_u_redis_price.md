# 取uredis价格信息-DescribeURedisPrice

取uredis价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Size|int|量大小,单位:GB  取值范围[1-32]|**Yes**|
|ChargeType|string|计费模式，Year， Month， Dynamic；如果不指定，则一次性获取三种计费|No|
|Quantity|int|计费模式为Dynamic时，购买的时长, 默认为1|No|
|RegionFlag|bool|是否是跨机房URedis(默认false)|No|
|ProductType|string|产品类型：MS_Redis（标准主备版），S_Redis（从库），默认为MS_Redis|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|价格 参数见 UMemPriceSet|No|

## URedisPriceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|Year， Month， Dynamic，Trial|No|
|Price|float|价格，单位: 元，保留小数点后两位有效数字|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeURedisPrice
&Region=cn-bj2
&Zone=cn-bj2-02
&Size=1
&ChargeType=Month
&Quantity=1
```

# Response Example
```
{
    "Action": "DescribeURedisPriceResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Price": 8000, 
            "ChargeType": "Month"
        }
    ]
}
```

