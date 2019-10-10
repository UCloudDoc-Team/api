# 获取负载均衡信息-DescribeULB

获取ULB详细信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|Offset|int|数据偏移量，默认为0|No|
|Limit|int|数据分页值，默认为20|No|
|ULBId|string|负载均衡实例的Id。 若指定则返回指定的负载均衡实例的信息； 若不指定则返回当前数据中心中所有的负载均衡实例的信息|No|
|VPCId|string|ULB所属的VPC|No|
|SubnetId|string|ULB所属的子网ID|No|
|BusinessId|string|ULB所属的业务组ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的ULB总数|No|
|DataSet|array|ULB列表，每项参数详见 ULBSet|No|

## ULBSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ULBId|string|负载均衡的资源ID|No|
|ULBName|string|负载均衡的资源名称(内部记载，废弃)|No|
|Name|string|负载均衡的资源名称（资源系统中），缺省值“ULB”|No|
|Tag|string|负载均衡的业务组名称，缺省值“Default”|No|
|Remark|string|负载均衡的备注，缺省值“”|No|
|BandwidthType|int|带宽类型，枚举值为： 0，非共享带宽； 1，共享带宽|No|
|Bandwidth|int|带宽|No|
|CreateTime|int|ULB的创建时间，格式为Unix Timestamp|No|
|ExpireTime|int|ULB的到期时间，格式为Unix Timestamp|No|
|Resource|array|ULB的详细信息列表（废弃）|No|
|IPSet|array|ULB的详细信息列表，具体结构见下方 ULBIPSet|No|
|VServerSet|array|负载均衡实例中存在的VServer实例列表，具体结构见下方 ULBVServerSet|No|
|ULBType|string|ULB 的类型|No|
|VPCId|string|ULB所在的VPC的ID|No|
|SubnetId|string|ULB 为 InnerMode 时，ULB 所属的子网ID，默认为空|No|
|BusinessId|string|ULB 所属的业务组ID|No|
|PrivateIP|string|ULB的内网IP，当ULBType为OuterMode时，该值为空|No|

## ULBIPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|OperatorName|string|弹性IP的运营商信息，枚举值为：  Bgp：BGP IP International：国际IP|No|
|EIP|string|弹性IP地址|No|
|EIPId|string|弹性IP的ID|No|
|BandwidthType|int|弹性IP的带宽类型，枚举值：1 表示是共享带宽，0 普通带宽类型（暂未对外开放）|No|
|Bandwidth|int|弹性IP的带宽值（暂未对外开放）|No|

## ULBVServerSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|MonitorType|string|健康检查类型，枚举值：Port -> 端口检查；Path -> 路径检查；|**Yes**|
|Domain|string|根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查域名|**Yes**|
|Path|string|根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查路径|**Yes**|
|VServerId|string|VServer实例的Id|No|
|VServerName|string|VServer实例的名字|No|
|Protocol|string|VServer实例的协议。 枚举值为：HTTP，TCP，UDP，HTTPS。|No|
|FrontendPort|int|VServer服务端口|No|
|Method|string|VServer负载均衡的模式，枚举值：Roundrobin -> 轮询;Source -> 源地址；ConsistentHash -> 一致性哈希；SourcePort -> 源地址（计算端口）；ConsistentHashPort -> 一致性哈希（计算端口）。|No|
|PersistenceType|string|VServer会话保持方式。枚举值为： None -> 关闭会话保持； ServerInsert -> 自动生成； UserDefined -> 用户自定义。|No|
|PersistenceInfo|string|根据PersistenceType确定： None或ServerInsert，此字段为空； UserDefined，此字段展示用户自定义会话string。|No|
|ClientTimeout|int|空闲连接的回收时间，单位：秒。|No|
|Status|int|VServer的运行状态。枚举值： 0 -> rs全部运行正常;1 -> rs全部运行异常；2 -> rs部分运行异常。|No|
|SSLSet|array|VServer绑定的SSL证书信息，具体结构见下方 ULBSSLSet|No|
|BackendSet|array|后端资源信息列表，具体结构见下方 ULBBackendSet|No|
|ListenType|string|监听器类型，枚举值为: RequestProxy -> 请求代理；PacketsTransmit -> 报文转发|No|
|PolicySet|array|内容转发信息列表，具体结构见下方 ULBPolicySet|No|

## ULBSSLSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SSLId|string|SSL证书的Id|No|
|SSLName|string|SSL证书的名字|No|
|SSLType|string|SSL证书类型，暂时只有 Pem 一种类型|No|
|SSLContent|string|SSL证书的内容|No|
|CreateTime|int|SSL证书的创建时间|No|
|SSLBindedTargetSet|array|SSL证书绑定到的对象|No|

## ULBBackendSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BackendId|string|后端资源实例的Id|No|
|ResourceType|string|资源实例的类型|No|
|ResourceId|string|资源实例的资源Id|No|
|ResourceName|string|资源实例的资源名称|No|
|SubResourceType|string|资源绑定的虚拟网卡实例的类型|No|
|SubResourceId|string|资源绑定的虚拟网卡实例的资源Id|No|
|SubResourceName|string|资源绑定的虚拟网卡实例的资源名称|No|
|PrivateIP|string|后端提供服务的内网IP|No|
|Port|int|后端提供服务的端口|No|
|Enabled|int|后端提供服务的实例启用与否，枚举值：0 禁用 1 启用|No|
|Status|int|后端提供服务的实例运行状态，枚举值：0健康检查健康状态 1 健康检查异常|No|
|SubnetId|string|后端提供服务的资源所在的子网的ID|No|

## ULBPolicySet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|PolicyId|string|内容转发Id，默认内容转发类型下为空。|No|
|PolicyType|string|内容类型，枚举值：Custom -> 客户自定义；Default -> 默认内容转发|No|
|Type|string|内容转发匹配字段的类型，枚举值：Domain -> 域名；Path -> 路径； 默认内容转发类型下为空|No|
|Match|string|内容转发匹配字段;默认内容转发类型下为空。|No|
|PolicyPriority|int|内容转发优先级，范围[1,9999]，数字越大优先级越高。默认内容转发规则下为0。|No|
|VServerId|string|所属VServerId|No|
|TotalCount|int|默认内容转发类型下返回当前rs总数|No|
|BackendSet|array|内容转发下rs的详细信息，参考PolicyBackendSet|No|

## PolicyBackendSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BackendId|string|所添加的后端资源在ULB中的对象ID，（为ULB系统中使用，与资源自身ID无关|No|
|ObjectId|string|后端资源的对象ID|No|
|Port|int|所添加的后端资源服务端口|No|
|PrivateIP|string|后端资源的内网IP|No|
|ResourceName|string|后端资源的实例名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeULB
&Region=cn-bj2
&ProjectId=project-XXXXX
```

# Response Example
```
{
    "Action": "DescribeULBResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Remark": "", 
            "VPCId": "uvnet-XXX", 
            "Name": "ULB", 
            "BusinessId": "", 
            "IPSet": [], 
            "ULBId": "ulb-XXXX", 
            "VServerSet": [
                {
                    "Status": 0, 
                    "PersistenceType": "None", 
                    "ListenType": "RequestProxy", 
                    "Protocol": "HTTP", 
                    "PersistenceInfo": "", 
                    "PolicySet": [
                        {
                            "BackendSet": [
                                {
                                    "ResourceName": "test", 
                                    "BackendId": "backend-XXXXX", 
                                    "Port": 80, 
                                    "ObjectId": "b47f082b-684f-4d5c-8dc4-XXXXX", 
                                    "PrivateIP": "10.25.XXX.17"
                                }
                            ], 
                            "PolicyPriority": 0, 
                            "VServerId": "vserver-XXXX", 
                            "TotalCount": 1, 
                            "PolicyType": "Default", 
                            "PolicyId": "", 
                            "Type": "", 
                            "Match": ""
                        }
                    ], 
                    "VServerId": "vserver-XXXX", 
                    "SSLSet": [], 
                    "Domain": "", 
                    "CreateTime": 1529909432, 
                    "MetricIdSet": [
                        {
                            "MetricId": "69538bf3-00bc-4385-85cc-XXXX", 
                            "Type": "OuterMode"
                        }
                    ], 
                    "VServerName": "VServer", 
                    "BackendSet": [
                        {
                            "Status": 0, 
                            "ResourceType": "UHost", 
                            "ResourceId": "uhost-XXXX", 
                            "Enabled": 1, 
                            "BackendId": "backend-XXXX", 
                            "PrivateIP": "10.25.XXX.17", 
                            "SubnetId": "subnet-hi50vf", 
                            "ResourceName": "test", 
                            "Port": 80
                        }
                    ], 
                    "Path": "", 
                    "ClientTimeout": 60, 
                    "Method": "Roundrobin", 
                    "FrontendPort": 80, 
                    "MonitorType": "Port"
                }
            ], 
            "PrivateIP": "", 
            "Bandwidth": 0, 
            "Tag": "Default", 
            "ULBType": "OuterMode", 
            "SubnetId": "", 
            "CreateTime": 1529909322, 
            "BandwidthType": 0
        }
    ]
}
```

