# 更新内容转发规则-UpdatePolicy

更新内容转发规则，包括转发规则后的服务节点

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|ULBId|string|需要添加内容转发策略的负载均衡实例ID|**Yes**|
|VServerId|string|需要添加内容转发策略的VServer实例ID|**Yes**|
|PolicyId|string|转发规则的ID|**Yes**|
|BackendId.n|string|内容转发策略应用的后端资源实例的ID，来源于 AllocateBackend 返回的 BackendId|**Yes**|
|Match|string|内容转发匹配字段|**Yes**|
|Type|string|内容转发匹配字段的类型|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PolicyId|string|转发规则的ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=UpdatePolicy
&Region=cn-bj2
&ProjectId=org-0axxmd
&PolicyId=0a074d02-b7c9-4a5d-9acf-414081f1b85f
&Match=ok
&ULBId=ulb-kix54p
&VServerId=vserver-9b646b
&BackendId.0=backend-67a442
```

# Response Example
```
{
    "Action": "CreatePolicyResponse", 
    "PolicyId": "0a074d02-b7c9-4a5d-9acf-414081f1b85f", 
    "RetCode": 0
}
```

