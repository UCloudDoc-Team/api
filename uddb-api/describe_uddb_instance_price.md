# 获取分布式数据库UDDB价格-DescribeUDDBInstancePrice

获取分布式数据库UDDB价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|DataNodeDiskSpace|int|新的数据节点的磁盘大小配置. 单位: GB 具体数值参考UDB的磁盘大小取值.|**Yes**|
|RouterVersion|string|UDDB路由节点的版本。分为三种： Trival(免费版)： 2中间件节点； QPS：1.5WFeelFree(标准版)： 固定为4中间件节点，后续将根据业务请求量自动扩展，最多扩展到12个节点，QPS为3w - 10w；EnjoyAlone(物理机版)：专享物理机，节点数让客户可选|**Yes**|
|RouterNodeNum|int|其他版本：该参数可不填；专享版：物理机节点个数。一台物理机有2个节点|**Yes**|
|DataNodeCount|int|初始的数据节点个数 取值必须>0.|**Yes**|
|DataNodeMemory|string|新的数据节点的内存配置, 单位：MB 具体数值参考UDB的内存取值.|**Yes**|
|ChargeType|string|付费类型，可选值如下: Year: 按年付费 Month: 按月付费 Dynamic: 按需付费(单位: 小时) Trial: 免费试用 默认值为: Dynamic|No|
|Quantity|int|购买时长，默认值1|No|
|DataNodeSlaveCount|int|每个数据节点的只读实例个数, 取值必须>=0. 默认取值为0.|No|
|InstanceMode|string|存储节点的高可用模式， 分为高可用UDB（HA）和普通UDB（Normal），如果不填， 则默认为HA|No|
|InstanceType|string|存储节点和只读实例的磁盘类型。分为：SSD磁盘（SATA_SSD）或普通磁盘(Normal)。 如果不填，则默认为SATA_SSD|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|如果执行失败, 失败的错误消息|No|
|PriceInfo|array|价格明细, 参考PriceInfo对象定义|No|

## PriceInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|付费类型|No|
|Price|float|价格|No|
|PriceName|string|产品名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDDBInstancePrice
&Region=cn-zj
&Zone=cn-zj-01
&ChargeType=jqinQilx
&Quantity=7
&RouterVersion=Trival
&RouterNodeNum=2
&DataNodeCount=3
&DataNodeMemory=CVblcUbp
&DataNodeDiskSpace=6
&DataNodeSlaveCount=6
```

# Response Example
```
{
    "Action": "DescribeUDDBInstancePriceResponse", 
    "RetCode": 0, 
    "PriceInfo": {
        "MiddlewarePrice": 1234.56, 
        "DataNodeSlavePrice": 6543.21, 
        "DataNodePrice": 6543.21
    }
}
```

