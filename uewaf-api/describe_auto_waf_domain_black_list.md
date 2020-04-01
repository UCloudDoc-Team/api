# 查询自动添加黑名单策略-DescribeAutoWafDomainBlackList

查询自动添加黑名单策略

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Rows|array|自动拦截策略列表，参考AutoWafDomainBlackList|No|
|TotalCount|int|自动拦截策略数量|No|

## AutoWafDomainBlackList
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Id|int|规则ID|**Yes**|
|FullName|string|规则所属域名|**Yes**|
|AttackType|string|攻击类型|**Yes**|
|ActionType|string|防御模式|**Yes**|
|AttackCount|int|攻击数量|**Yes**|
|IntervalTime|int|攻击统计区间，单位:秒|**Yes**|
|ExpiredTime|int|攻击过期区间，单位:秒|**Yes**|
|Enable|int|启用状态;Enable启用,否则禁用|**Yes**|
|CreateTime|string|创建时间|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeAutoWafDomainBlackList
&FullDomain=IYJAvYuo
&Offset=1
&Limit=7
&ProjectId=xtSqRxhE
```

# Response Example
```
{
    "Action": "DescribeAutoWafDomainBlackListResponse", 
    "TotalCount": 8, 
    "Rows": [
        "ZzwxHvJP"
    ], 
    "RetCode": 0
}
```

