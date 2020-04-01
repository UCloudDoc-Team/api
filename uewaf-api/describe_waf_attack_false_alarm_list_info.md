# 获取误报记录列表-DescribeWafAttackFalseAlarmListInfo

获取误报记录列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Domain|string|要查询的域名|**Yes**|
|Offset|int|记录 偏移，等效于PageNum|No|
|Limit|int|记录限制数目，等效于PageSize|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|误报记录数量|**Yes**|
|DetailList|array|误报记录列表|**Yes**|

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
https://api.ucloud.cn/?Action=DescribeWafAttackFalseAlarmListInfo
&Domain=uSvMPpes
&Offset=9
&Limit=1
```

# Response Example
```
{
    "Action": "DescribeWafAttackFalseAlarmListInfoResponse", 
    "TotalCount": 4, 
    "DetailList": [
        "KViSuMZT", 
        "KFwPWDfZ", 
        "iEnQMPNi", 
        "ONIovEYv", 
        "qSzqBjgn", 
        "YTsYINIe", 
        "svmJWVny", 
        "qTVQqbzI", 
        "dkrLJCwK"
    ], 
    "RetCode": 0
}
```

