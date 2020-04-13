# 查询信息安全过滤规则-DescribeWafResponseFilter

查询信息安全过滤规则

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
|Data|array|信息安全过滤规则列表，参考HttpReponseFilter|**Yes**|

## HttpReponseFilter
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ID|int|规则ID|No|
|Name|string|规则名称|No|
|Type|string|防护类型；可选项：Status（状态码），Sensitive（敏感内容），Customize（自定义字符串）|No|
|Content|string|过滤内容|No|
|RuleAction|string|丢弃响应或伪装内容|No|
|DisguiseFile|string|伪装响应内容|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafResponseFilter
&ProjectId=org-xxx
&FullDomain=www.test.com
```

# Response Example
```
{
    "Action": "DescribeWafHttpResponseFilterResponse", 
    "Data": [
        {
            "Name": "手机号", 
            "Content": "TelNum", 
            "RuleAction": "DROP", 
            "DisguiseFile": "", 
            "Type": "Sensitive", 
            "ID": 3000
        }, 
        {
            "Name": "43", 
            "Content": "403", 
            "RuleAction": "DISGUISE", 
            "DisguiseFile": "403403", 
            "Type": "Status", 
            "ID": 2000
        }, 
        {
            "Name": "404", 
            "Content": "404", 
            "RuleAction": "DROP", 
            "DisguiseFile": "", 
            "Type": "Status", 
            "ID": 1000
        }
    ], 
    "RetCode": 0
}
```

