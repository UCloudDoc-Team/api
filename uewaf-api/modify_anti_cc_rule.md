# 修改CC防御规则-ModifyAntiCCRule

修改CC防御规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|要修改的规则ID|**Yes**|
|Reqs|int|统计时长内请求次数|**Yes**|
|URL|string|请求的uri|**Yes**|
|Mode|string|URI匹配模式，equal:完全匹配;,contains:包含;|**Yes**|
|Duration|int|统计时长,单位：秒|**Yes**|
|ActionType|string|触发条件后执行的动作，forbidden:拦截请求； captcha:验证码；iptables：IP封堵|**Yes**|
|Validity|int|动作有效期，单位：分钟|**Yes**|
|Domain|string|添加CC防护规则的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyAntiCCRule
&ProjectId=PCSaxEVD
&ID=8
&Domain=eZaFQvVy
&Reqs=8
&URL=yChTaoNC
&Mode=equal
&Duration=3
&ActionType=forbidden
&Validity=6
```

# Response Example
```
{
    "Action": "ModifyAntiCCRuleResponse", 
    "RetCode": 0
}
```

