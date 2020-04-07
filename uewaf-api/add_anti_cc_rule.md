# 添加CC防御规则-AddAntiCCRule

添加CC防御规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Domain|string|要添加防护规则的域名|**Yes**|
|Reqs|int|统计时长内的请求数|**Yes**|
|URL|string|uri，eg：/index.html|**Yes**|
|Mode|string|匹配模式，equal:完全匹配；contains:包含|**Yes**|
|Duration|int|统计时长,单位： 秒|**Yes**|
|ActionType|string|匹配后执行的动作，forbidden:拦截请求；captcha:验证码； iptables：IP封堵|**Yes**|
|Validity|int|动作有效期，单位：分钟|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功后返回的规则ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddAntiCCRule
&ProjectId=org-xxx
&Domain=www.test.com
&Reqs=55000
&URL=/index.html
&Mode=equal
&Duration=2800
&ActionType=forbidden
&Validity=5720
```

# Response Example
```
{
    "Action": "AddAntiCCRuleResponse", 
    "Id": 6, 
    "RetCode": 0
}
```

