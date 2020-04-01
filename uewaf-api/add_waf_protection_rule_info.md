# 添加waf防护规则-AddWafProtectionRuleInfo

添加waf防护规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|RuleNum|int|规则匹配条件个数|**Yes**|
|RuleName|string|规则名称|**Yes**|
|RuleAction|string|规则命中之后的动作，Deny:拦截，Accept|**Yes**|
|RiskRank|string|风险等级，Low:低,Middle:中,High:高|**Yes**|
|Rule.0|string|规则匹配条件，举例：Field:UserAgent,Operator:Contain,Content:xxxx|**Yes**|
|FullDomain|string|要添加防护规则的域名|**Yes**|
|RiskType|string|风险种类；可选值：scan,loopholes,xss,cc,sql,exec,webshell,infoleak,eaa,protocol,other|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功后返回的防护规则ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddWafProtectionRuleInfo
&RecordId=9
&RuleNum=1
&RuleName=MPxZbVdj
&RuleAction=Deny
&RiskRank=Low
&Rule.n=oIXASoNp
&FullDomain=wjshscRk
&RiskType=cJFdSWYJ
&ProjectId=qheqbXHc
```

# Response Example
```
{
    "Action": "AddWafProtectionRuleInfoResponse", 
    "RetCode": 0, 
    "Id": 9
}
```

