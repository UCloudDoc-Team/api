# 获取升级价格-DescribeUMemUpgradePrice

获取UMem升级价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Size|int|购买UMem大小,单位:GB|**Yes**|
|Type|string|空间类型:single(无热备),double(热备)(默认: double)|**Yes**|
|SpaceId|string|需要升级的空间的SpaceId|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|int|价格(兼容老版本)|No|
|DataSet|object|价格|No|

## PriceDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TotalPrice|int|升降级资源的价格|No|
|CustomPrice|int|用户折后价|No|
|PurchaseValue|int|资源有效期|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUMemUpgradePrice
&Region=cn-bj2
&Zone=
&Size=16
&Type=double
&SpaceId=umem-mXXXX
```

# Response Example
```
{
    "Action": "DescribeUMemUpgradePriceResponse", 
    "Price": 4, 
    "RetCode": 0, 
    "DataSet": {}
}
```

