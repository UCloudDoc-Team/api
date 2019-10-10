# 更新VServer属性-UpdateVServerAttribute

更新VServer实例属性

```
VServerId 对应 CreateVServer 返回的 VServerId
或者 DescribeVServer / DescribeULB 返回的 ULBVServerSet 中的 VServerId

没有传的参数都不会做修改
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ULBId|string|负载均衡实例ID|**Yes**|
|VServerId|string|VServer实例ID|**Yes**|
|VServerName|string|VServer实例名称，若无此字段则不做修改|No|
|Method|string|VServer负载均衡模式，枚举值：Roundrobin -> 轮询;Source -> 源地址；ConsistentHash -> 一致性哈希；SourcePort -> 源地址（计算端口）；ConsistentHashPort -> 一致性哈希（计算端口）; WeightRoundrobin -> 加权轮询; Leastconn -> 最小连接数。ConsistentHash，SourcePort，ConsistentHashPort 只在报文转发中使用；Leastconn只在请求代理中使用；Roundrobin、Source和WeightRoundrobin在请求代理和报文转发中使用。默认为："Roundrobin"|No|
|PersistenceType|string|VServer会话保持模式，若无此字段则不做修改。枚举值：None：关闭；ServerInsert：自动生成KEY；UserDefined：用户自定义KEY。|No|
|PersistenceInfo|string|根据PersistenceType确定: None或ServerInsert, 此字段无意义; UserDefined, 则此字段传入用户自定义会话保持String. 若无此字段则不做修改|No|
|ClientTimeout|int|请求代理的VServer下表示空闲连接的回收时间，单位：秒，取值范围：时(0，86400]，默认值为60；报文转发的VServer下表示回话保持的时间，单位：秒，取值范围：[60，900]，0 表示禁用连接保持|No|
|MonitorType|string|健康检查的类型，Port:端口,Path:路径|No|
|Domain|string|MonitorType 为 Path 时指定健康检查发送请求时HTTP HEADER 里的域名|No|
|Path|string|MonitorType 为 Path 时指定健康检查发送请求时的路径，默认为 /|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateVServerAttribute
&Region=cn-bj2
&ProjectId=project-XXXXX
&ULBId=ulb-XXXX
&VServerId=vserver-XXXX
&VServerName=Testapi
&Protocol=HTTP 
&Method=Roundrobin
&PersistenceType=None
&PersistenceInfo=None
&ClientTimeout=60
&MonitorType=Port
```

# Response Example
```
{
    "Action": "UpdateVServerAttributeResponse", 
    "RetCode": 0
}
```

