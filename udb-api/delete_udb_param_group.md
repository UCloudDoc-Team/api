# 删除配置-DeleteUDBParamGroup

删除配置参数组

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|GroupId|int|参数组id,可通过DescribeUDBParamGroup获取|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUDBParamGroup
&Region=cn-bj2
&Zone=cn-bj2-04
&GroupId=192
```

# Response Example
```
{
    "Action": "DeleteUDBParamGroupResponse", 
    "RetCode": 0
}
```

