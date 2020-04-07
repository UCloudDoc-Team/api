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
|Enable|int|启用状态;1表示启用,0表示禁用|**Yes**|
|CreateTime|string|创建时间|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeAutoWafDomainBlackList
&ProjectId=org-xxx
&FullDomain=www.test.com
```

# Response Example
```
{
    "Action": "DescribeAutoWafDomainBlackListResponse", 
    "TotalCount": 2, 
    "Rows": [
        {
            "FullDomain": "www.test.com", 
            "Enable": 1, 
            "AttackCount": 10, 
            "IntervalTime": 60, 
            "CreateTime": 1585192039, 
            "ExpireTime": 60, 
            "ActionType": "forbidden", 
            "AttackType": "all", 
            "Id": 591
        }, 
        {
            "FullDomain": "www.test.com", 
            "Enable": 1, 
            "AttackCount": 10, 
            "IntervalTime": 60, 
            "CreateTime": 1585878780, 
            "ExpireTime": 60, 
            "ActionType": "forbidden", 
            "AttackType": "protocol", 
            "Id": 603
        }
    ], 
    "RetCode": 0
}
```

