# 删除子账号-TerminateMember

删除管理员人员管理页面的指定子账号

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|MemberEmail|string|用户邮箱|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=TerminateMember&MemberEmail=example@ucloud.cn
```

# Response Example
```
{
    "Action": "TerminateMemberResponse", 
    "RetCode": 0
}
```

