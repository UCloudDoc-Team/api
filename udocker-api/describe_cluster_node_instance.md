# 获取节点-DescribeClusterNodeInstance

获取节点

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ClusterId|string|集群实例Id |**Yes**|
|NodeIds.n|string|节点实例ID, 如果为空, 则返回当前Cluster所有符合条件的节点；n=0,1,2...|No|
|Offset|int|数据偏移量, 默认为0|No|
|Limit|int|返回数据长度, 默认为20，最大值10000000|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的总数|No|
|NodeSet|string|节点实例列表, 每项参数可见NodeSet结构|No|

## NodeSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NodeId|string|节点实例ID|No|
|NodeType|string|主机类型  Normal：标准机型，SSD：SSD机型)|No|
|Remark|string|备注|No|
|Name|string|实例名称|No|
|State|string|实例状态, 初始化:Initializing, 启动中:Starting, 运行中:Running, 关机中:Stopping,关机:Stopped, 安装失败:Install Fail, 重启中:Rebooting   |No|
|CreateTime|int|创建时间，格式为unix时间戳|No|
|ChargeType|string|计费类型  Year, Month, Dynamic,Trial|No|
|ExpireTime|int|到期时间，格式 为unix时间戳|No|
|UsedMem|int|已使用内存|No|
|UsedCPU|float|已使用cpu|No|
|ContainerCount|int|节点上容器个数|No|
|CPU|float|虚拟CPU核数, 单位:个|No|
|Memory|int|内存大小, 单位:MB|No|
|AutoRenew|string|是否自动续费，自动续费：“Yes”，不自动续费：“No”|No|
|DiskSet|string|磁盘信息|No|
|NetCapability|string|网络能力，目前的值有Normal 和 Super|No|
|IPSet|string|IP信息|No|

## IPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Type|string|IP类型  国际:International, BGP:Bgp, 内网:Private|No|
|IPId|string|IP资源ID  （只在当前IP为外网IP时返回）|No|
|IP|string|IP地址|No|
|Bandwidth|int|IP对应的带宽, 单位:Mb （只在当前IP为外网IP时返回）|No|
|VPCId|string|VPCId|No|
|SubnetId|string|子网ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeClusterNodeInstance
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&ClusterId=cluster-xxx
&NodeIds.0=dnode-xxx
```

# Response Example
```
{
    "Action": "DescribeClusterNodeInstanceResponse", 
    "TotalCount": 0, 
    "NodeSet": [], 
    "RetCode": 0
}
```

