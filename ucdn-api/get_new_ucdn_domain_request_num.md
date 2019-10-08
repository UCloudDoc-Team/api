# 获取域名请求数-GetNewUcdnDomainRequestNum

获取域名请求数

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Type|int|时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天的粒度）|**Yes**|
|DomainId.n|string|域名id，创建域名时生成的id。默认全部域名|No|
|Areacode|string|查询区域 cn代表国内 abroad代表海外，只支持国内|No|
|BeginTime|int|查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。如没有赋值，则返回缺少参 数错误，如果没有EndTime，BeginTime也可以不赋值，EndTime默认当前时间，BeginTime 默认前一天的当前时间。|No|
|EndTime|int|查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RequestList|array|请求数实例表。|No|

## RequestInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|带宽获取的时间点。格式：时间戳|No|
|CdnRequest|double|返回值返回指定时间区间内的cdn收到的请求次数之和|No|
|OriginRequest|double|返回值返回指定时间区间内的cdn回源的请求次数之和）|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetNewUcdnDomainRequestNum
&ProjectId=xxxxx
&DomainId.n=DAqjTRaw
&Areacode=nXjmAdrO
&BeginTime=8
&EndTime=5
&Type=3
```

# Response Example
```
{
    "Action": "GetNewUcdnDomainRequestNumResponse", 
    "RequestList": [
        {
            "OriginRequest": 6, 
            "CdnRequest": 1, 
            "Time": 4
        }, 
        {
            "OriginRequest": 5, 
            "CdnRequest": 9, 
            "Time": 5
        }, 
        {
            "OriginRequest": 4, 
            "CdnRequest": 7, 
            "Time": 6
        }
    ], 
    "RetCode": 0
}
```

