# 删除单机Memcache-DeleteUMemcacheGroup

删除单机Memcache

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|GroupId|string|组ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUMemcacheGroup
&Region=cn-east-01
&GroupId=umemcache-00f986
```

# Response Example
```
{
    "Action": "DeleteUMemcacheGroupResponse", 
    "RetCode": 0
}
```

