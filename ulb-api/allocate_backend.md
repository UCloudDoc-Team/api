# 添加后端实例-AllocateBackend

添加ULB后端资源实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ULBId|string|负载均衡实例的ID|**Yes**|
|VServerId|string|VServer实例的ID|**Yes**|
|ResourceType|string|所添加的后端资源的类型，枚举值：UHost -> 云主机；UPM -> 物理云主机； UDHost -> 私有专区主机；UDocker -> 容器，默认值为“UHost”|**Yes**|
|ResourceId|string|所添加的后端资源的资源ID|**Yes**|
|Port|int|所添加的后端资源服务端口，取值范围[1-65535]，默认80|No|
|Weight|int|所添加的后端RS权重（在加权轮询算法下有效），取值范围[0-100]，默认为1|No|
|Enabled|int|后端实例状态开关，枚举值： 1：启用； 0：禁用 默认为启用|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BackendId|string|所添加的后端资源在ULB中的对象ID，（为ULB系统中使用，与资源自身ID无关），可用于 UpdateBackendAttribute/UpdateBackendAttributeBatch/ReleaseBackend|No|

# Request Example
```
https://api.ucloud.cn/?Action=AllocateBackend
&Region=cn-bj2
&ProjectId=project-XXXXX
&ULBId=ulb-XXXXX
&VServerId=vserver-XXXXX
&ResourceType=UHost
&ResourceId=uhost-XXXX 
&Port=80
&Enabled=1
&Weight=4
```

# Response Example
```
{
    "Action": "AllocateBackendResponse", 
    "RetCode": 0, 
    "BackendId": "backend-XXXXX"
}
```

