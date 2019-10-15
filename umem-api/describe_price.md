# 获取价格-DescribeUMemPrice

获取UMem实例价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Size|int|购买umem大小,单位:GB,范围[1~1024]|**Yes**|
|Type|string|空间类型:single(无热备),double(热备)(默认: double)|**Yes**|
|ChargeType|string|Year， Month， Dynamic，Trial 如果不指定，则一次性获取三种计费|No|
|Quantity|int|购买UMem的时长，默认值为1|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|价格 参数见 UMemPriceSet|No|

## UMemPriceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|Year， Month， Dynamic，Trial|No|
|Price|float|价格，单位: 元，保留小数点后两位有效数字|No|

# Request Example
```
https://api.ucloud.cn/udisk/?Action=DescribeUMemPrice
&Region=cn-north-02
&Zone=cn-bj2-04
&Size=1   
&Type=double
&ChargeType=Month
&Quantity=12
```

# Response Example
```
{
    "Action": "DescribeUMemPriceResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Price": 1360, 
            "ChargeType": "Month"
        }
    ]
}
```

