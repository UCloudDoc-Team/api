# 获取指定域名的攻击行为概览-DescribeWafAttackSummaryInfo

获取指定域名的攻击行为概览

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BeginTime|int|起始时间戳|No|
|FullDomain|string|域名，为空则查询所有域名|No|
|EndTime|int|截止时间戳|No|
|SearchType.n|string|统计类别数组，默认"attack,uri,client,riskrank"|No|
|AttackType|string|攻击统计类型，查询 IP TOP10 时生效，默认全选；参数选项: protocol: 协议违规, xss: XSS攻击, sql: SQL注入, loopholes: 漏洞攻击, exec: 命令执行, webshell: WebShell上传, eaa: 越权访问, infoleak: 信息泄露, scan: 恶意扫描, cc: CC攻击, other: 其他|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Data|object|返回数据|No|

## WafAttackSummaryInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AttackTypeDistribution|array|{AttackType: "cc", AttackName: "CC攻击", AttackCount: 9}|No|
|RiskRankDistribution|array|{RiskRankType: "High", Priority: 0, AttackCount: 3}|No|
|TimeAxisDistribution|array|{Time: 1564653600, AcceptCount: 0, DenyCount: 0}|No|
|TopAttackIP|array|{SrcIp: "120.132.23.61", AttackCount: 3,IPDB:{}}|No|
|TopAttackUri|array|{AttackUrl: "/test2", AttackCount: 7}|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafAttackSummaryInfo
&RecordId=PHnNFvWI
&TimeType=Hour
&BeginTime=7
&EndTime=3
&FullDomain=ADbhhBow
&SearchType=VKvaNpnd
&AttackType=vDHXzBEG
```

# Response Example
```
{
    "Action": "DescribeWafAttackSummaryInfoResponse", 
    "Data": {}, 
    "RetCode": 0
}
```

