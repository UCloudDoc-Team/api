# 添加信息安全过滤规则-AddWafResponseFilter

添加信息安全过滤规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要添加规则的域名|**Yes**|
|Name|string|规则名称|**Yes**|
|Type|string|过滤类型；可选项：Status（状态码），Sensitive（敏感内容），Customize（自定义字符串）。|**Yes**|
|RuleAction|string|丢弃响应或伪装内容；可选项：DROP（丢弃响应），DISGUISE（伪装内容）|**Yes**|
|Content|string|过滤内容。当过滤类型为Sensitive时为可选项，可选值：Identity（身份证号），TelNum（手机号），Email（邮件）|No|
|DisguiseFile|string|伪装响应内容|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ID|int|添加的规则ID|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=AddWafResponseFilter
&ProjectId=org-xxx
&FullDomain=www.test.com
&Name=test
&Type=Status
&Content=404
&RuleAction=DROP
```

# Response Example
```
{
    "Action": "AddWafResponseFilterResponse", 
    "ID": 2, 
    "RetCode": 0
}
```

