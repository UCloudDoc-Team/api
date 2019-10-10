# 更新内容转发组属性-UpdatePolicyGroupAttribute

更新内容转发策略组属性

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|GroupId|string|内容转发策略组ID|**Yes**|
|GroupName|string|修改策略转发组名称|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdatePolicyGroupAttribute
&Region=cn-bj2
&GroupId=ulb-fr-2axjbg
&GroupName=new-policy-name
```

# Response Example
```
{
    "Action": "UpdatePolicyGroupAttributeResponse", 
    "RetCode": 0
}
```

