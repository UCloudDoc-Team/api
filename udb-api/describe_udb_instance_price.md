# 获取云数据库价格-DescribeUDBInstancePrice

获取UDB实例价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|MemoryLimit|int|内存限制(MB)，单位为MB.目前支持：1000-96000|**Yes**|
|DiskSpace|int|磁盘空间(GB),暂时支持20(GB) - 3000(GB), 输入不带单位|**Yes**|
|DBTypeId|string|UDB实例的DB版本字符串|**Yes**|
|Count|int|购买DB实例数量,最大数量为10台, 默认为1台|No|
|ChargeType|string|Year，按年付费； Month，按月付费 Dynamic，按需付费（需开启权限) Trial，试用（需开启权限）默认为月付|No|
|Quantity|int|DB购买多少个"计费时间单位"，默认值为1。比如：买2个月，Quantity就是2。如果计费单位是“按月”，并且Quantity为0，表示“购买到月底”|No|
|UseSSD|string|是否使用SSD，只能填true或false，默认为false|No|
|SSDType|string|SSD类型，可选值为"SATA"、"PCI-E"，如果UseSSD为true ，则必填|No|
|InstanceMode|string|实例的部署类型。可选值为：Normal: 普通单点实例，Slave: 从库实例,HA: 高可用部署实例，默认是Normal|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|价格 参照UDBInstancePriceSet|No|

## UDBInstancePriceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|Year， Month， Dynamic，Trial|No|
|Price|int|价格，单位为分|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBInstancePrice
&Region=cn-bj2
&Zone=cn-bj2-04
&Count=1   
&ChargeType=Month   
&Quantity=12
&MemoryLimit=600
&DiskSpace=20
&DBTypeId=mysql-5.5
```

# Response Example
```
{
    "Action": "DescribeUDBInstancePriceResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Price": 1360, 
            "ChargeType": "Month"
        }
    ]
}
```

