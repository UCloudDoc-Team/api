# 升级UDDB时，获取升级后的价格-DescribeUDDBInstanceUpgradePrice

升级UDDB时，获取升级后的价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UDDBId|string|UDDB实例ID|**Yes**|
|RouterVersion|string|UDDB路由节点的版本。分为三种： Trival(免费版)： 2中间件节点； QPS：1.5WFeelFree(标准版)： 固定为4中间件节点，后续将根据业务请求量自动扩展，最多扩展到12个节点，QPS为3w - 10w；EnjoyAlone(物理机版)：专享物理机，节点数让客户可选|**Yes**|
|RouterNodeNum|int|其他版本：该参数可不填；专享版：物理机节点的个数。一台物理机有2个节点|**Yes**|
|DataNodeCount|int|新的数据节点个数 取值必须>0.|No|
|DataNodeMemory|int|新的数据节点的内存配置, 单位：MB 具体数值参考UDB的内存取值.|No|
|DataNodeDiskSpace|int|新的数据节点的磁盘大小配置. 单位: GB 具体数值参考UDB的磁盘大小取值.|No|
|DataNodeSlaveCount|int|每个数据节点的只读实例个数, 取值必须>=0.|No|
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
|MiddlewarePrice|float|中间件路由节点费用|No|
|DataNodePrice|float|存储节点费用|No|
|DataNodeSlavePrice|float|只读实例费用|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDDBInstanceUpgradePrice
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=RNmZhzsX
&RouterNodeVersion=Trival
&RouterNodeNum=2
&DataNodeCount=2
&DataNodeMemory=8
&DataNodeDiskSpace=7
&DataNodeSlaveCount=9
&InstanceMode=nHhQyjwr
&InstanceType=PBXTsHdq
&ProjectId=WZUxpnBL
```

# Response Example
```
{
    "Action": "DescribeUDDBInstanceUpgradePriceResponse", 
    "Message": "NhfvJDKU", 
    "RetCode": 0, 
    "PriceInfo": [
        {
            "MiddlewarePrice": 4.88913, 
            "DataNodeSlavePrice": 1.77679, 
            "DataNodePrice": 3.76372
        }, 
        {
            "MiddlewarePrice": 6.95267, 
            "DataNodeSlavePrice": 7.28714, 
            "DataNodePrice": 2.24776
        }, 
        {
            "MiddlewarePrice": 5.64989, 
            "DataNodeSlavePrice": 7.37894, 
            "DataNodePrice": 1.25864
        }, 
        {
            "MiddlewarePrice": 2.15365, 
            "DataNodeSlavePrice": 9.76949, 
            "DataNodePrice": 4.35778
        }, 
        {
            "MiddlewarePrice": 6.88811, 
            "DataNodeSlavePrice": 8.91499, 
            "DataNodePrice": 8.12559
        }, 
        {
            "MiddlewarePrice": 1.87756, 
            "DataNodeSlavePrice": 6.32137, 
            "DataNodePrice": 6.31617
        }, 
        {
            "MiddlewarePrice": 6.55247, 
            "DataNodeSlavePrice": 6.76566, 
            "DataNodePrice": 5.51924
        }, 
        {
            "MiddlewarePrice": 1.75898, 
            "DataNodeSlavePrice": 8.19212, 
            "DataNodePrice": 3.61715
        }, 
        {
            "MiddlewarePrice": 4.19762, 
            "DataNodeSlavePrice": 7.22914, 
            "DataNodePrice": 5.64282
        }, 
        {
            "MiddlewarePrice": 4.84727, 
            "DataNodeSlavePrice": 1.26237, 
            "DataNodePrice": 6.65527
        }
    ]
}
```

