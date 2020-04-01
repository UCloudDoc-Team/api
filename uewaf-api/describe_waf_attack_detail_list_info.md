# 查询WAF攻击详情-DescribeWafAttackDetailListInfo

查询WAF攻击详情

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，不填表示默认项目|No|
|TimeType|string|时间格式，支持1小时、一天、七天和自定义，默认一天|No|
|AttackType|string|攻击类型["scan", "loopholes", "xss", "cc", "sql", "exec", "webshell", "infoleak", "eaa", "protocol", "other"]|No|
|RiskRank|string|风险级别|No|
|ActionType|string|匹配动作，拦截、放行、告警|No|
|Offset|string|页面偏移|No|
|Limit|string|每页数量限制|No|
|SortArray|string|排序方式|No|
|BeginTime|int|自定义开始时间|No|
|EndTime|int|自定义结束时间|No|
|FullDomain|string|要查询的域名，为空RecordId 为0时，查询全部|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DetailList|array|攻击详情列表，参考WafAttack|No|
|TotalCount|int|攻击详情总数|No|

## WafAttack
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|区域|No|
|Protocol|string|协议|No|
|ServerName|string|服务器名称|No|
|DestIp|string|目标IP地址|No|
|Port|string|端口|No|
|Alerts|array|告警匹配信息，参考WafAlert|No|
|RequestHeaders|object|http请求头部信息，参考RequestHeader|No|
|Attack|string|攻击类型|No|
|Method|string|请求方法|No|
|FalsePositive|bool|是否误报|No|
|RiskRank|string|风险等级|No|
|TimeStamp|int|攻击时间戳|No|
|Host|string|主机名|No|
|Referer|string|引用地址|No|
|Count|string|攻击次数|No|
|Uri|string|URI|No|
|Client|string|客户端|No|
|Mode|string|工作模式|No|
|Action|string|匹配动作|No|
|UA|string|用户代理|No|
|ClientIPInfo|object|客户端位置信息，参考CityInfo|No|
|Args|string|参数|No|

## WafAlert
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Description|string|规则描述|No|
|Match|object|匹配规则|No|
|Id|string|匹配规则ID|No|

## RequestHeader
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AcceptLanguage|string|接收语言类型|No|
|AcceptEncoding|string|支持编码类型|No|
|Host|string|主机|No|
|Accept|string|数据类型|No|
|UpgradeInsecureRequests|string|http升级到https请求|No|
|Connection|string|连接方式|No|
|Cookie|string|Cookie|No|
|CacheControl|string|缓存行为|No|
|UserAgent|string|用户代理|No|
|XForwardFor|string|XFF|No|

## CityInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CountryName|string|国家|No|
|RegionName|string|区域|No|
|CityName|string|城市|No|
|OwnerDomain|string|所属域名|No|
|Latitude|string|纬度|No|
|Longitude|string|经度|No|
|Timezone|string|时区|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafAttackDetailListInfo
&AttackType=dInUvelh
&ActionType=aGvvYUBb
&RiskRank=OvslWVzB
&Domain=OCqqCWsM
&TimeType=RRgoJMUF
&Offset=veYqdbQA
&Limit=htCILfrP
&SortArray=jaUdGwQZ
&BeginTime=4
&EndTime=urxhLFWZ
&ProjectId=TDekVwDC
```

# Response Example
```
{
    "Action": "DescribeWafAttackDetailListInfoResponse", 
    "TotalCount": 5, 
    "RetCode": 0, 
    "DetailList": [
        "FIJbGkum"
    ]
}
```

