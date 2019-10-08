# 修改名称-ModifyURedisGroupName

修改主备redis名称

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|GroupId|string|组的ID|**Yes**|
|Name|string|Redis组名称 (范围[6-63],只能包含英文、数字以及符号-和_)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyURedisGroupName
&Region=cn-north-02
&GroupId=uredis-opqm12
&Name=NewName
&ProjectId=org-quk5zs
```

# Response Example
```
{
    "Action": "ModifyURedisGroupNameResponse", 
    "RetCode": 0
}
```

