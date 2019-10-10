# 获取Container实例-DescribeContainerInstance

获取Container实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NodeId|string|容器所属节点ID|No|
|ClusterId|string|容器所属资源池ID|No|
|ContainerIds.n|string|容器ID|No|
|Offset|int|偏移量，默认为0|No|
|Limit|int|总量限制，默认20，最大值10000|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总数|**Yes**|
|ContainerSet|array|容器列表|No|

## ContainerSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ContainerId|string|容器ID|No|
|ClusterId|string|集群ID|No|
|NodeId|string|节点ID|No|
|Name|string|容器名|No|
|Image|string|容器镜像|No|
|Zone|string|可用区|No|
|CPU|float|CPU个数|No|
|Memory|int|内存容量，MB|No|
|Cmd|string|容器启动命令|No|
|State|string|状态|No|
|IPSet|array|IP|No|
|CreateTime|int|Unix时间戳|No|
|Volume|string|容器内挂载的目录|No|
|Enviroment|array|环境变量|No|

## IPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Type|string|国际: Internation，BGP: Bgp，内网: Private|No|
|IPId|string|IP资源ID (内网IP无对应的资源ID)|No|
|IP|string|IP地址|No|
|Bandwidth|int|IP对应的带宽, 单位: Mb (内网IP不显示带宽信息)|No|
|Default|string|是否默认的弹性网卡的信息。true: 是默认弹性网卡；其他值：不是。|No|

## EnviromentSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Key|string|key:val形式|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeContainerInstance
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&NodeId=dnode-xxx
&ClusterId=cluster-xxx
&Offset=0
&Limit=100
```

# Response Example
```
{
    "Action": "DescribeContainerInstanceResponse", 
    "TotalCount": 2, 
    "ContainerSet": [
        {
            "Parameters": {
                "log-opt": [
                    "max-file=2", 
                    "max-size=10M"
                ]
            }, 
            "Enviroment": [
                {
                    "TZ": "Asia/Shanghai"
                }
            ], 
            "State": "RUNNING", 
            "Memory": 0, 
            "CPU": 0, 
            "Zone": "cn-bj2-02", 
            "IPSet": [
                {
                    "IP": "10.10.xxx.xxx", 
                    "Type": "Private"
                }
            ], 
            "RegionId": 1000001, 
            "ClusterId": "cluster-xxx", 
            "Volume": "", 
            "Name": "service22-pod", 
            "Cmd": "", 
            "NodeId": "dnode-xxx", 
            "PortMap": "", 
            "ContainerType": "pod", 
            "ContainerId": "docker-xxx", 
            "Weight": 100, 
            "ClusterName": "cluster2", 
            "ComputerDetails": {
                "all_mem": 8192, 
                "vpc_id": "uvnet-xxx", 
                "subnet_id": "subnet-xxx", 
                "res_id": "dnode-xxx", 
                "all_cpus": 4
            }, 
            "Image": "uhub.service.ucloud.cn/ucloud/centos6-ssh:latest", 
            "TaskId": "docker-xxx", 
            "SvcName": "service22", 
            "CreateTime": 1529986046
        }, 
        {
            "Parameters": {
                "log-opt": [
                    "max-file=2", 
                    "max-size=10M"
                ]
            }, 
            "Enviroment": [
                {
                    "TZ": "Asia/Shanghai"
                }
            ], 
            "State": "RUNNING", 
            "Memory": 0, 
            "CPU": 0, 
            "Zone": "cn-bj2-02", 
            "IPSet": [
                {
                    "IP": "10.10.xxx.xxx", 
                    "Type": "Private"
                }
            ], 
            "RegionId": 1000001, 
            "ClusterId": "cluster-xxx", 
            "Volume": ":/data", 
            "Name": "Container", 
            "Cmd": "", 
            "NodeId": "dnode-xxx", 
            "PortMap": "", 
            "ContainerType": "container", 
            "ContainerId": "docker-xxx", 
            "Weight": 0, 
            "ClusterName": "cluster2", 
            "ComputerDetails": {
                "all_mem": 8192, 
                "vpc_id": "uvnet-xxx", 
                "subnet_id": "subnet-xxx", 
                "res_id": "dnode-xxx", 
                "all_cpus": 4
            }, 
            "Image": "uhub.service.ucloud.cn/ucloud/centos6-ssh:latest", 
            "TaskId": "docker-xxx", 
            "SvcName": "", 
            "CreateTime": 1529985617
        }
    ], 
    "RetCode": 0
}
```

