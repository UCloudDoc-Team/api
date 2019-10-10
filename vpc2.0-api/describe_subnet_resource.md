# 展示子网资源-DescribeSubnetResource

展示子网资源

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SubnetId|string|子网id|**Yes**|
|ResourceType|string|资源类型，默认为全部资源类型。枚举值为：UHOST，云主机；PHOST，物理云主机；ULB，负载均衡；UHADOOP_HOST，hadoop节点；UFORTRESS_HOST，堡垒机；UNATGW，NAT网关；UKAFKA，Kafka消息队列；UMEM，内存存储；DOCKER，容器集群；UDB，数据库；UDW，数据仓库；VIP，内网VIP.|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|单页返回数据长度，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总数|No|
|DataSet|array|返回数据集，请见SubnetResource|No|

## SubnetResource
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|资源名称|No|
|ResourceId|string|资源Id|No|
|ResourceType|string|资源类型。对应的资源类型：UHOST，云主机；PHOST，物理云主机；ULB，负载均衡；UHADOOP_HOST，hadoop节点；UFORTRESS_HOST，堡垒机；UNATGW，NAT网关；UKAFKA，Kafka消息队列；UMEM，内存存储；DOCKER，容器集群；UDB，数据库；UDW，数据仓库；VIP，内网VIP.|No|
|SubResourceName|string|资源绑定的虚拟网卡的实例名称|No|
|SubResourceId|string|资源绑定的虚拟网卡的实例ID|No|
|SubResourceType|string|资源绑定的虚拟网卡的类型|No|
|IP|string|资源ip|No|
|IPv6Address|string|资源的IPv6地址|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeSubnetResource
&Region=cn-sh2
&ProjectId=org-XXXX
&SubnetId=subnet-XXXXX
&ResourceType=VIP
&Offset=1
&Limit=5
```

# Response Example
```
{
    "Action": "DescribeSubnetResourceResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "ResourceType": "VIP", 
            "IP": "10.23.XX.25", 
            "Name": "VIP", 
            "ResourceId": "vip-XXXX"
        }
    ]
}
```

