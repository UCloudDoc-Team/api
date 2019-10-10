# 升降级分布式数据库数据节点的配置-UpgradeUDDBDataNode

升降级分布式数据库数据节点的配置, 提高/降低数据节点的数据容量和内存

所有数据节点以及其所挂载的只读实例的配置都受到影响

升降级数据节点的配置之后之后, 会按照数据节点新的磁盘和内存大小重新计费

如下状态的数据节点实例可以进行这个操作:

Shutoff: 已关闭
当请求返回成功之后，UDDB实例的状态变成"UpgradingDataNode"，相关数据节点的状态变成"Upgrading"; 如果返回失败, UDDB实例状态保持不变 当UDDB实例升级结束之后, UDDB实例的状态变成"Shutoff"

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|UDDBId|string|UDDB实例ID|**Yes**|
|DataNodeMemory|int|新的数据节点的内存配置, 单位：MB 具体数值参考UDB的内存取值|**Yes**|
|DataNodeDiskSpace|int|新的数据节点的磁盘大小配置. 单位: GB 具体数值参考UDB的磁盘大小取值.|**Yes**|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|如果执行失败, 失败的错误消息|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpgradeUDDBDataNode
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=zuLSTdbI
&DataNodeMemory=8
&DataNodeDiskSpace=2
&CouponId=BIYpPZeJ
```

# Response Example
```
{
    "Action": "UpgradeUDDBDataNodeResponse", 
    "Message": "ZkwoeTyN", 
    "RetCode": 0
}
```

