# 调整防护规则优先级至最高或者最低-ModifyWafProtectionPriorityPoleInfo

调整防护规则优先级至最高或者最低

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要操作的域名|**Yes**|
|RuleSetID|int|规则ID|**Yes**|
|Pole|string|优先级调整策略|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafProtectionPriorityPoleInfo
&ProjectId=org-xxx
&FullDomain=www.test.com
&RuleSetID=45000
&Pole=Top
```

# Response Example
```
{
    "Action": "ModifyWafProtectionPriorityPoleInfoResponse", 
    "RetCode": 0
}
```

