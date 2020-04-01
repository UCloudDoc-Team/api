# 查询指定域名的系统默认规则-DescribeWafSystemRules

查询指定域名的系统默认规则

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
|Rules|array|规则内容列表，参考SystemRuleInfo|No|

## SystemRuleInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SysRuleset|int|规则起始编号|No|
|Action|string|动作|No|
|RiskRank|string|风险等级|No|
|RulesetType|string|规则集类型|No|
|Priority|int|优先级|No|
|AttackType|string|攻击类型|No|
|Description|string|规则描述|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafSystemRules
&ProjectId=LCnpfpWv
&FullDomain=ExtJVSbp
```

# Response Example
```
{
    "Action": "DescribeWafSystemRulesResponse", 
    "Rules": [
        "qADiCIeE"
    ], 
    "RetCode": 0
}
```

