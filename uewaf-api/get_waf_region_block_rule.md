# 查询区域IP封堵规则-GetWafRegionBlockRule

查询区域IP封堵记录

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|查询域名 |**Yes**|
|Offset|int|分页查询偏移设置|**Yes**|
|Limit|int|单页数量限制|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Count|int|规则数量|No|
|RuleList|object|规则列表，参考RegionBlackInfo|No|

## RegionBlackInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ID|int|规则ID|No|
|Name|string|规则名称|No|
|FullDomain|string|所属域名|No|
|Action|string|执行动作|No|
|Regions|string|生效区域|No|
|Description|string|规则描述|No|
|TopOrganizationId|int|用户ID|No|
|OrganizationId|int|项目ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetWafRegionBlockRule
&ProjectId=org-xxx
&FullDomain=www.test.com
&Offset=0
&Limit=10
```

# Response Example
```
{
    "Action": "GetWafRegionBlockRuleResponse", 
    "Count": 1, 
    "RetCode": 0, 
    "RuleList": [
        {
            "FullDomain": "*.8cname.com", 
            "Description": "全部", 
            "OrganizationId": 50148127, 
            "TopOrganizationId": 50146955, 
            "Regions": "!CN", 
            "Action": "Deny", 
            "ID": 1115, 
            "Name": "1"
        }
    ]
}
```

