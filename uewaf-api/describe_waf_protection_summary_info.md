# 获取防护规则列表-DescribeWafProtectionSummaryInfo

获取防护规则列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要查询的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|规则数量|No|
|WorkMode|string|工作模式|No|
|RuleSetList|array|规则集列表，参考ProtectionSummaryRuleSetEntry|No|

## ProtectionSummaryRuleSetEntry
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RuleName|string|规则名称|No|
|RuleAction|string|规则动作|No|
|Priority|int|优先级|No|
|RiskRank|string|风险等级|No|
|RiskType|string|风险类型|No|
|RuleSetID|int|规则集ID|No|
|RuleSetType|string|规则集类型|No|
|SysRuleset|int|规则集起始ID|No|
|RuleDescription|string|规则描述|No|
|RuleList|array|规则详情，参考ProtectionSummaryRuleInfo|No|

## ProtectionSummaryRuleInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Field|string|匹配字段|No|
|Operator|string|行为动作|No|
|Content|string|匹配内容|No|
|RuleId|int|规则ID|No|
|Description|string|规则描述|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafProtectionSummaryInfo
&ProjectId=org-xxx
&FullDomain=www.test.com
```

# Response Example
```
{
    "Action": "DescribeWafProtectionSummaryInfoReponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "WorkMode": "Alarm", 
    "RuleSetList": [
        {
            "RiskType": "scan", 
            "RuleList": [
                {
                    "UserRuleId": 45001, 
                    "Description": "", 
                    "RuleId": 45000, 
                    "Content": "2.2.2.2", 
                    "Field": "SrcIp", 
                    "Operator": "Contain"
                }
            ], 
            "RuleSetID": 45000, 
            "RuleSetType": "", 
            "RiskRank": "High", 
            "RuleDescription": "", 
            "Priority": 0, 
            "Location": "root", 
            "RuleAction": "Deny", 
            "RuleName": "test", 
            "Phase": "access", 
            "SysRuleset": 90045000
        }
    ]
}
```

