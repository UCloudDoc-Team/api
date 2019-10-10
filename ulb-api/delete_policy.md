# 删除转发策略-DeletePolicy

删除内容转发策略

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|PolicyId|string|内容转发策略ID|**Yes**|
|GroupId|string|内容转发策略组ID|No|
|VServerId|string|VServer 资源ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeletePolicy
&Region=cn-bj2
&ProjectId=project-xs13ik
&GroupId=ulb-fr-2axjbg
&PolicyId=0a074d02-b7c9-4a5d-9acf-414081f1b85f
```

# Response Example
```
{
    "Action": "DeletePolicyResponse", 
    "RetCode": 0
}
```

