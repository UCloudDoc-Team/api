# 删除WAF防护规则-DeleteWafProtectionRuleInfo

删除WAF防护规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|RuleSetID|int|要删除的规则集ID|**Yes**|
|FullDomain|string|要删除的防护规则所属域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWafProtectionRuleInfo
&ProjectId=org-xxx
&RuleSetID=46000
&FullDomain=www.test.com

```

# Response Example
```
{
    "Action": "DeleteWafProtectionRuleInfoResponse", 
    "RetCode": 0
}
```

