# 编辑自定义防护规则-ModifyWafProtectionCustomerInfo

编辑自定义防护规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|RuleSetID|int|规则ID|**Yes**|
|RuleName|string|规则名称|**Yes**|
|RiskRank|string|规则风险等级|**Yes**|
|RuleAction|string|规则匹配后的动作|**Yes**|
|RuleNum|int|规则匹配条件个数|**Yes**|
|RiskType|string|风险种类，scan,loopholes,xss,cc,sql,exec,webshell,infoleak,eaa,protocol,other|**Yes**|
|FullDomain|string|域名， 域名与域名ID 必须选填一项|**Yes**|
|Rule|string|规则匹配条件|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafProtectionCustomerInfo
&ProjectId=dZTaaQCt
&RuleSetID=1
&RuleName=IvBFRtXf
&RiskRank=Low
&RuleAction=Deny
&RuleNum=7
&Rule.n=SdmFaonG
&FullDomain=qAfVNlnZ
&RiskType=PakiNZBM
```

# Response Example
```
{
    "Action": "ModifyWafProtectionCustomerInfoResponse", 
    "RetCode": 0
}
```

