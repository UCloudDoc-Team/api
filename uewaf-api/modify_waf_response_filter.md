# 修改信息安全过滤规则-ModifyWafResponseFilter

修改信息安全过滤规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|要修改的规则ID|**Yes**|
|FullDomain|string|要操作的域名|**Yes**|
|Name|string|规则名称|**Yes**|
|Type|string|	过滤类型；可选项：Status（状态码），Sensitive（敏感内容），Customize（自定义字符串）|**Yes**|
|RuleAction|string|丢弃响应或伪装内容；可选项：DROP（丢弃响应），DISGUISE（伪装内容）|**Yes**|
|Content|string|过滤内容|No|
|DisguiseFile|string|伪装响应内容|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafResponseFilter
&ProjectId=org-xxx
&ID=6
&FullDomain=www.test.com
&Name=test
&Type=Status
&RuleAction=DROP
&Content=404
```

# Response Example
```
{
    "Action": "ModifyWafResponseFilterResponse", 
    "RetCode": 0
}
```

