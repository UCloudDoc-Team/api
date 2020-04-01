# 批量复制WAF规则-CopyWafDomainRules

批量复制WAF规则，目前支持防护规则、CC规则、恶意IP惩罚规则、黑白名单、返回码防护规则的复制

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|源域名|**Yes**|
|DestDomain.n|string|目的域名|**Yes**|
|RuleType|string|规则类型,CCRule:CC规则； ProtectionRule：防护规则； AutoBlacklistRule：自动拦截规则； HTTPDisguiseRule：信息防护规则； RegionBlockRule：区域封堵规则；WhiteList：白名单规则；BlackList：黑名单规则|**Yes**|
|Append|bool|赋值方式是否追加；true：追加，false：覆盖；默认未覆盖|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CopyWafDomainRules
&ProjectId=ytxpNUYj
&FullDomain=JrVjmkbm
&DestDomain.n=iHfnTEcP
&RuleType=kAiLRYfq
&Append=false
```

# Response Example
```
{
    "Action": "CopyWafDomainRulesResponse", 
    "RetCode": 0
}
```

