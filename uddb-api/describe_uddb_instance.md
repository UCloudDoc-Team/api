# 获取分布式数据库UDDB的详细信息-DescribeUDDBInstance

获取分布式数据库UDDB的详细信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|UDDBId|string|UDDB实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|如果执行失败, 失败的错误消息|No|
|DataSet|array|UDDB实例信息列表, 参见DataSetUDDB项定义|No|

## DataSetUDDB
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|UDDB实例对应的可用区|No|
|UDDBId|string|UDDB实例ID|No|
|Name|string|UDDB实例名称|No|
|DBTypeId|string|UDDB的数据库版本|No|
|AdminUser|string|管理员帐户名，默认root|No|
|VirtualIP|string|UDDB实例访问的虚IP|No|
|Port|string|UDDB实例访问的端口号|No|
|State|string|UDDB状态, 状态列表如下: Init: 初始化中 InitFail: 初始化失败 Starting: 启动中 Running: 系统正常运行中 Abnormal: 系统运行中, 有异常, 还能提供服务 Error: 系统运行中, 但不能正常提供服务 Shutdown: 关闭中 Shutoff: 已关闭 Deleted: 已删除 UpgradingUDDB: 升降级UDDB配置中 UpgradingDataNode: 升降级UDDB节点配置中 ChangingSlaveCount: 改变只读实例数量中 ScalingOutUDDB: 水平扩展中|No|
|CreateTime|string|UDDB实例创建时间，采用UTC计时时间戳|No|
|ExpiredTime|string|UDDB实例过期时间，采用UTC计时时间戳|No|
|ChargeType|string|付费类型，可选值如下: Year: 按年付费 Month: 按月付费 Dynamic: 按需付费(单位: 小时) Trial: 免费试用|No|
|RouterVersion|string|UDDB路由节点的版本。分为三种： Trival(免费版)： 2中间件节点； QPS：1.5W FellFree(标准版)： 固定为4中间件节点，后续将根据业务请求量自动扩展，最多扩展到12个节点，QPS为3w - 10w； EnjoyAlone(物理机版)：专享物理机，节点数让客户可选|No|
|RouterNodeNum|int|各版本下的节点个数。体验版： 固定为2节点； 畅享版：固定为4节点（后续可通过管理API调整）；专享版：物理机台数|No|
|RefQps|int|参考QPS。 免费版： 15000； 畅享版： 30000 - 100000 （根据节点数而定）； 专享版： 节点数 * 10w qps|No|
|DataNodeCount|string|数据节点个数|No|
|DataNodeMemory|string|数据节点的内存配置, 单位：MB|No|
|DataNodeDiskSpace|string|数据节点的磁盘大小配置. 单位: GB|No|
|DataNodeSlaveCount|string|每个数据节点的只读实例个数.|No|
|DataNodeList|array|UDDB实例的数据节点的信息列表|No|
|InstanceMode|string|存储节点的高可用模式， 分为高可用UDB（HA）和普通UDB（Normal），如果不填， 则默认为HA|No|
|InstanceType|string|存储节点和只读实例的磁盘类型。分为：SSD磁盘（SATA_SSD）或普通磁盘(Normal)。 如果不填，则默认为SATA_SSD|No|

## DataNodeInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Id|string|数据节点ID|No|
|Memory|string|数据节点的内存配置, 单位：MB|No|
|DiskSpace|string|数据节点的磁盘大小配置. 单位: GB|No|
|SlaveCount|string|数据节点的只读实例个数.|No|
|State|string|数据分片状态, 状态列表如下: Init: 初始化中 Fail: 安装失败 Starting: 启动中 Running: 系统正常运行中 Shutdown: 关闭中 Shutoff: 已关闭 Deleted: 已删除 Upgrading: 系统升级中|No|
|SlaveInfos|array|只读实例信息列表|No|
|LastTransTaskId|string|最近一次数据迁移任务id|No|
|CreateTime|string|节点的创建时间|No|

## SlaveInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NodeType|object|集群中slave的机型信息|No|
|SlaveCount|int|集群中slave的数量|No|

## NodeType
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NodeTypeName|string|机型名称|No|
|CPU|int|CPU核数|No|
|Memory|int|内存数量|No|
|CU|int|计算单元数量|No|
|Disk|int|磁盘大小|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDDBInstance
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=SyzHzCdW
```

# Response Example
```
{
    "Action": "DescribeUDBInstanceResponse", 
    "RetCode": 0, 
    "DataSet": {
        "DataNodeDiskSpace": 100, 
        "DataNodeMemory": 6000, 
        "DBTypeId": "mysql-5.6", 
        "CPUCores": 4, 
        "DataNodeList": [
            {
                "DiskSpace": 50, 
                "SlaveCount": 1, 
                "State": "Running", 
                "Memory": 3000, 
                "Id": "uddbnode-mst001", 
                "SlaveInfos": [
                    {
                        "DataNodeId": "uddbnode-mst001", 
                        "State": "Running", 
                        "Id": "uddbnode-slv001"
                    }
                ]
            }, 
            {
                "DiskSpace": 50, 
                "SlaveCount": 1, 
                "State": "Running", 
                "Memory": 3000, 
                "Id": "uddbnode-mst002", 
                "SlaveInfos": [
                    {
                        "DataNodeId": "uddbnode-mst002", 
                        "State": "Running", 
                        "Id": "uddbnode-slv002"
                    }
                ]
            }
        ], 
        "DBId": "udb-abcdef", 
        "InstanceType": "SATA_SSD", 
        "VirtualIP": "10.19.123.123", 
        "InstanceMode": "HA", 
        "State": "Running", 
        "ExpiredTime": 1501516800, 
        "DataNodeCount": 2, 
        "Memory": 8000, 
        "DataNodeSlaveCount": 1, 
        "Name": "my_test_uddb1", 
        "Port": 3306, 
        "CreateTime": 1403249482, 
        "AdminUser": "root"
    }
}
```

