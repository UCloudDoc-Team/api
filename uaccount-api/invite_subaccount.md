# 邀请子帐号成员-InviteSubaccount

邀请子帐号成员

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UserEmail|string|受邀成员邮箱地址，不得重复|**Yes**|
|UserPhone|string|受邀成员手机号码|**Yes**|
|UserName|string|受邀成员姓名|**Yes**|
|IsFinance|string|是否有财务权限(true:是,false:否,默认为否)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=InviteSubaccount
&UserEmail=lOqBhhkG
&UserPhone=SBwrZBSY
&UserName=mdHhPdnD
&IsFinance=IvixWFse
```

# Response Example
```
{
    "Action": "InviteSubaccountResponse", 
    "RetCode": 0
}
```

