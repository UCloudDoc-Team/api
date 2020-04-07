# 添加域名黑名单-AddWafDomainBlackList

添加域名黑名单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要添加黑名单的域名|**Yes**|
|Source|string|黑名单来源， 用户自定义(custom)/机器行为检测(bot)/ bot-rule/ auto（自动拦截规则）|**Yes**|
|Type|string|类型：境内(internal)、境外(oversea)，自定义(custom)|**Yes**|
|ActionType|string|执行动作: 可选值:拦截请求(forbidden) ，验证码(captcha)|**Yes**|
|ExpireTime|int|过期时间,即有效时长，单位为秒,永不过期传0|**Yes**|
|DestIp|string|目标IP; Source为bot时需传递|No|
|CIDRS.n|string|IP、网段或者IP段，传递数组；类型为custom时必填|No|
|Remark|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功后返回的域名黑名单ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddWafDomainBlackList
&ProjectId=org-xxx
&FullDomain=www.test.com
&Source=custom
&Type=custom
&ActionType=forbidden
&CIDRS.0=2.2.2.2
&ExpireTime=10
&Remark=test
```

# Response Example
```
{
    "Action": "AddWafDomainBlackListResponse", 
    "RetCode": 0, 
    "Id": 6
}
```

