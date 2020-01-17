# 更新后端实例属性-UpdateBackendAttribute

更新ULB后端资源实例(服务节点)属性

!> 报文转发的服务节点暂不支持修改 Port；BackendId 对应的是 AllocateBackend 返回的 BackendId 或者 DescribeULB/DescribeVServer 返回的 ULBBackendSet 结构体中的 BackendId

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ULBId|string|负载均衡资源ID|**Yes**|
|BackendId|string|后端资源实例的ID(ULB后端ID，非资源自身ID)|**Yes**|
|Port|int|后端资源服务端口，取值范围[1-65535]|No|
|Weight|int|所添加的后端RS权重（在加权轮询算法下有效），取值范围[0-100]，默认为1|No|
|Enabled|int|后端实例状态开关|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateBackendAttribute
&Region=cn-bj2
&ProjectId=project-XXXX
&ULBId=ulb-XXXX
&BackendId=backend-XXXX
&Port=8080
&Enabled=0
&Weight=2
```

# Response Example
```
{
    "Action": "UpdateBackendAttributeResponse", 
    "RetCode": 0
}
```

