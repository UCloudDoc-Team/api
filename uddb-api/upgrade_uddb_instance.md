# 升降级分布式数据库中间件的配置-UpgradeUDDBInstance

升降级分布式数据库中间件的配置, 提高/降低请求处理的并发性

修改请求处理节点个数之后, 按照所有请求处理节点的总内存容量和CPU核数重新计费

如下状态的UDDB实例可以进行这个操作:

Running: 系统正常运行中
当请求返回成功之后，UDDB实例的状态变成"UpgradingUDDB"; 如果返回失败, UDDB实例状态保持不变 当UDDB实例升级成功之后, UDDB实例的状态变成"Running"; 如果更改过程中出现异常, 状态变成"Abnormal", 或者"Error"

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|UDDBId|string|UDDB实例ID|**Yes**|
|RouterVersion|string|UDDB路由节点的版本。分为三种： Trival(免费版)： 2中间件节点； QPS：1.5W FellFree(标准版)： 固定为4中间件节点，后续将根据业务请求量自动扩展，最多扩展到12个节点，QPS为3w - 10w； EnjoyAlone(物理机版)：专享物理机，节点数让客户可选|**Yes**|
|RouterNodeNum|int|其他版本：该参数可不填；专享版：物理机台数|**Yes**|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|如果执行失败, 失败的错误消息|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpgradeUDDBInstance
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=pSyBgGsz
&NewRouterVersion=Trival
&NewRouterNodeNum=2
&CouponId=RvAhidRT
```

# Response Example
```
{
    "Action": "UpgradeUDDBInstanceResponse", 
    "Message": "iUhGtWka", 
    "RetCode": 0
}
```

