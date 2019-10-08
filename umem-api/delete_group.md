# 删除主备redis-DeleteURedisGroup

删除主备redis

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|GroupId|string|组ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteURedisGroup
&Region=cn-east-01
&GroupId=uredis-00f98D
```

# Response Example
```
{
    "Action": "DeleteURedisGroupResponse", 
    "RetCode": 0
}
```

