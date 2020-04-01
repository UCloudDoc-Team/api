# 获取域名攻击次数-DescribeWafDomainAttackCount

获取域名当日攻击次数

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，不填为默认项目|No|
|FullDomain|string|域名，不填时查询该用户账号下所有域名的当日攻击数|No|
|BeginTime|int|查询开始时间，不填默认为最近1天|No|
|EndTime|int|查询结束时间|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|AttackCount|int|攻击次数|**Yes**|
|RequestCount|int|请求总数|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafDomainAttackCount
&FullDomain=yTBBOfcy
&BeginTime=4
&EndTime=2
&BeginTime=8
```

# Response Example
```
{
    "Action": "DescribeWafDomainAttackCountResponse", 
    "AttackCount": 1, 
    "RequestCount": 2, 
    "RetCode": 0
}
```

