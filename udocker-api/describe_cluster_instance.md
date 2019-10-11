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
|ClusterId|string|集群实例ID|**Yes**|
|UsedMem|int|已使用内存|No|
|UsedCPU|int|已使用cpu|No|
|Memory|int|总内存|No|
|CPU|string|总cpu|No|
|ClusterName|string|集群名称|No|
|NodeCount|int|集群中所包含的主机数|No|
|CreateTime|int|创建时间, 格式为unix时间戳|No|
|VPCId|string|VPCId|No|

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

