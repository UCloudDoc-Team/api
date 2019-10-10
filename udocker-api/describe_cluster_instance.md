# 获取Cluster实例-DescribeClusterInstance

获取Cluster实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ClusterIds.n|string|Cluster实例ID,如果为空获取全部。n=0,1,2...|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|Container count|**Yes**|
|ClusterSet|string|Cluster实例set|No|

## ClusterSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UDWInstanceName|string|数据仓库名称|**Yes**|
|MasterNodeDomain|string|主节点域名|No|
|UDWInstanceId|string|数据仓库ID|**Yes**|
|NodeCount|int|节点个数|**Yes**|
|ExpireTime|int|计费过期时间|**Yes**|
|State|string|数据仓库状态|**Yes**|
|VPCId|string|虚拟私有云(VPC) ID|No|
|SubnetId|string|VPC中的子网ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeClusterInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&ClusterIds.0=cluster-xxx
```

# Response Example
```
{
    "Action": "DescribeClusterInstanceResponse", 
    "TotalCount": 1, 
    "ClusterSet": [
        {
            "VPCId": "uvnet-xxx", 
            "UsedCPU": "0.0", 
            "ClusterName": "cluster2", 
            "ClusterId": "cluster-xxx", 
            "UsedMem": 695, 
            "CPU": 8, 
            "Memory": 16384, 
            "NodeCount": 2, 
            "CreateTime": 1529984017
        }
    ], 
    "RetCode": 0
}
```

