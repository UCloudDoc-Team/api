# 修改自动拦截规则-ModifyAutoWafDomainBlackList

修改自动拦截规则，当检测到攻击后，自动将访问源IP加入黑名单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|需要修改的自动拦截规则ID|**Yes**|
|FullDomain|string|防御的域名，只能选择已添加的域名|**Yes**|
|AttackType|string|攻击种类，默认统计所有攻击种类|No|
|State|string|枚举值："Enable", "Disable"，控制规则是否生效|No|
|ActionType|string|检测到攻击后的动作， 默认为forbidden，支持captcha|No|
|ExpireTime|int|规则生效后， 添加黑名单的过期时间，单位分钟， 0 长期有效，默认60分钟|No|
|AttackCount|int|攻击阈值，默认10个|No|
|Interval|int|攻击统计区间，单位秒，默认60秒|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyAutoWafDomainBlackList
&ProjectId=USuwPxYg
&ID=2
&FullDomain=gCtmwlXB
&State=fmGWUSzE
&ActionType=OjYVhmxo
&ExpireTime=8
&AttackCount=8
&AttackType=UURJCxRc
&Interval=dTEukWvW
```

# Response Example
```
{
    "Action": "ModifyAutoWafDomainBlackListResponse", 
    "RetCode": 0
}
```

