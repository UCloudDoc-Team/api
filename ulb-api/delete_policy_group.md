# 删除内容转发组-DeletePolicyGroup

删除内容转发策略组

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|GroupId|string|内容转发策略组ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeletePolicyGroup
&Region=cn-bj2
&GroupId=ulb-fr-2axjbg
```

# Response Example
```
{
    "Action": "DeletePolicyGroupResponse", 
    "RetCode": 0
}
```

