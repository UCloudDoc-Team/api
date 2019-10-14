# 删除VServer-DeleteVServer

删除VServer实例

!> VServerId 对应 CreateVServer 返回的 VServerId
或者 DescribeVServer / DescribeULB 返回的 ULBVServerSet 中的 VServerId

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ULBId|string|负载均衡实例的ID|**Yes**|
|VServerId|string|VServer实例的ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteVServer
&Region=cn-bj2
&ProjectId=project-xs13ik
&ULBId=ulb-igw0gd
&VServerId=vserver-yuix67
```

# Response Example
```
{
    "Action": "DeleteVServerResponse", 
    "RetCode": 0
}
```

