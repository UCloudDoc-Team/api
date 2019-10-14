# 释放后端实例-ReleaseBackend

从VServer释放后端资源实例

!> VServer 为7层时，必须先把后端实例从转发规则中移除之后才能释放

BackendId 对应是 AllocateBackend 返回的 BackendId 
或者 DescribeULB/DescribeVServer 返回的 ULBBackendSet 里的 BackendId

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ULBId|string|负载均衡实例的ID|**Yes**|
|BackendId|string|后端资源实例的ID(ULB后端ID，非资源自身ID)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ReleaseBackend
&Region=cn-bj2
&ProjectId=project-xs13ik
&ULBId=ulb-a3qq0o
&BackendId=backend-d0d9e8
```

# Response Example
```
{
    "Action": "ReleaseBackendResponse", 
    "RetCode": 0
}
```

