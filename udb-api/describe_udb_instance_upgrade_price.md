# 获取UDB实例升降级价格信息-DescribeUDBInstanceUpgradePrice

获取UDB实例升降级价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|实例的Id|**Yes**|
|MemoryLimit|int|内存限制(MB)|**Yes**|
|DiskSpace|int|磁盘空间(GB), 暂时支持20G - 500G|**Yes**|
|UseSSD|bool|是否使用SSD，默认为false|No|
|SSDType|string|SSD类型，可选值为"SATA"、"PCI-E"，如果UseSSD为true ，则必选|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|int|价格，单位为分|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBInstanceUpgradePrice
&Region=cn-bj2
&DBId=udb-xxxxx
&MemoryLimit=2000
&DiskSpace=200
```

# Response Example
```
{
    "Action": "DescribeUDBInstanceUpgradePriceResponse", 
    "Price": 1360, 
    "RetCode": 0
}
```

