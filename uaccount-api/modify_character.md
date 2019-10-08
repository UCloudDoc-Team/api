# 修改角色-ModifyCharacter

修改角色

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CharacterId|string|角色ID|**Yes**|
|CharacterName|string|新角色名称|No|
|CharacterDescription|string|角色描述|No|
|Add.n|string|角色权限(增)|No|
|Del.n|string|角色权限(删)|No|
|Mod.n|string|角色权限(改)|No|
|Get.n|string|角色权限(查)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyCharacter
&CharacterId=qehEhJUw
&CharacterName=PmyyaiHK
&CharacterDescription=pGpdGkyB
&Add.n=llPVKzpb
&Del.n=ijIaeoEI
&Mod.n=CYtcuRJO
&Get.n=nGnUpKat
```

# Response Example
```
{
    "Action": "ModifyCharacterResponse", 
    "RetCode": 0
}
```

