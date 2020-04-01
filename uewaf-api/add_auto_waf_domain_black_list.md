# 创建自动拦截策略接口-AddAutoWafDomainBlackList

当检测到攻击后，自动将访问源IP加入黑名单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|防御的域名，只能选择已添加的域名|**Yes**|
|State|string|启用状态 Enable启用，否则禁用|No|
|AttackType|string|攻击统计类型，默认全选；参数选项: protocol: 协议违规, xss: XSS攻击, sql: SQL注入, loopholes: 漏洞攻击, exec: 命令执行, webshell: WebShell上传, eaa: 越权访问, infoleak: 信息泄露, scan: 恶意扫描, cc: CC攻击, other: 其他|No|
|ActionType|string|检测到攻击后的动作， 默认为forbidden，支持captcha|No|
|ExpireTime|int|添加黑名单的过期时间，单位分钟， 0 长期有效，默认60分钟|No|
|AttackCount|int|攻击阈值，默认10个|No|
|Interval|int|攻击统计区间，单位秒，默认60秒|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功返回的策略ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddAutoWafDomainBlackList
&ActionType=KFIHdcnx
&FullDomain=ryojENrI
&State=viBwqLqB
&ExpireTime=9
&AttackCount=8
&Interval=4
&RecordId=7
&ProjectId=cnQdEPkg
```

# Response Example
```
{
    "Action": "AddAutoWafDomainBlackListResponse", 
    "RetCode": 0, 
    "Id": 8
}
```

