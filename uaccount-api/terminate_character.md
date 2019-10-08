# 删除角色-TerminateCharacter

删除用户角色管理列表中的指定角色

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CharacterId|string|角色ID，使用DescribeCharacterList获取角色ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=TerminateCharacter
&CharacterId=JVnyLJNY
```

# Response Example
```
{
    "Action": "TerminateCharacterResponse", 
    "RetCode": 0
}
```

