# 修改主备密码-ModifyURedisGroupPassword

修改主备密码/重置密码

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|GroupId|string|组的ID|**Yes**|
|Password|string|新密码字符串，要求长度为6\~36个字符,且只能包含英文、数字以及-和下划线；并且需要base64加密；如要取消密码，此值为空字符串，|**Yes**|

?> 只能修改主实例密码，从实例禁止修改。

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyURedisGroupPassword
&Region=nMAgQwSo
&Zone=OXUwhOqN
&GroupId=CzmsTeDz
&ProjectId=dpZLfhxD
```

# Response Example
```
{
    "Action": "ModifyURedisGroupPasswordResponse", 
    "RetCode": 0
}
```

