# 获取误报记录列表-DescribeWafAttackFalseAlarmListInfo

获取误报记录列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Offset|int|记录 偏移，等效于PageNum|**Yes**|
|Limit|int|记录限制数目，等效于PageSize|**Yes**|
|Domain|string|要查询的域名，不填查询所有|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|误报记录总数|**Yes**|
|DetailList|array|误报记录列表，参考WafAttack|**Yes**|

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
|Count|int|攻击次数|No|
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
|Id|int|匹配规则ID|No|

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
&ProjectId=org-xxx
&Domain=www.test.com
&Offset=0
&Limit=10
```

# Response Example
```
{
    "Action": "DescribeWafAttackFalseAlarmListInfoResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DetailList": [
        {
            "Alerts": [
                {
                    "Description": "XSS", 
                    "Match": {
                        "1": "<script", 
                        "0": "<script", 
                        "2": "<", 
                        "5": "script"
                    }, 
                    "Id": 32003
                }
            ], 
            "AccessId": "183.238.16.138-a9736253", 
            "RequestBody": null, 
            "Attack": "xss", 
            "Method": "GET", 
            "ClientIPInfo": {
                "owner_domain": "", 
                "region_name": "广东", 
                "latitude": "22.547", 
                "longitude": "114.085947", 
                "city_name": "深圳", 
                "country_name": "中国", 
                "timezone": "Asia/Shanghai"
            }, 
            "Args": "", 
            "Host": "www.test.com", 
            "Referer": "NULL", 
            "TimeStamp": 1586240955, 
            "Region": "cn-bj", 
            "Count": 1, 
            "FalsePositive": true, 
            "RequestHeaders": {
                "XForwardFor": "", 
                "UpgradeInsecureRequests": "", 
                "Connection": "", 
                "Accept": "text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8", 
                "UserAgent": "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Win64; x64; Trident/4.0; .NET CLR 2.0.50727; SLCC2; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; Tablet PC 2.0)", 
                "Host": "www.test.com", 
                "Cookie": "", 
                "CacheControl": "", 
                "AcceptLanguage": "en-US", 
                "AcceptEncoding": ""
            }, 
            "ServerName": "www.test.com", 
            "RiskRank": "high", 
            "Uri": "/home.html?user=&password=&action!login:cantLogin%3Cscript%3Ealert(1344)%3C/script%3E=AppScan", 
            "DestIp": "106.75.79.224", 
            "Client": "183.238.16.138", 
            "Mode": "SIMULATE", 
            "TopId": 50146955, 
            "Action": "DENY", 
            "Protocol": "http", 
            "Port": "80", 
            "UA": "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Win64; x64; Trident/4.0; .NET CLR 2.0.50727; SLCC2; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; Tablet PC 2.0)", 
            "Id": "5e8c1dbb243527db1df82677"
        }
    ]
}
```

