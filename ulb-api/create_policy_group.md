# 创建内容转发组-CreatePolicyGroup

创建内容转发策略组

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|GroupName|string|内容转发策略组名称，默认为空|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|GroupId|string|内容转发策略组的Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreatePolicyGroup
&Region=cn-bj2
&GroupName=new-policy
```

# Response Example
```
{
    "Action": "CreatePolicyGroupResponse", 
    "GroupId": "ulb-fr-2axjbg", 
    "RetCode": 0
}
```

