# 冻结成员-FreezeMember

冻结成员

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|MemberEmail|string|需要被冻结的成员Email|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=FreezeMember
&MemberEmail=HZJXVMhb
```

# Response Example
```
{
    "Action": "FreezeMemberResponse", 
    "RetCode": 0
}
```

