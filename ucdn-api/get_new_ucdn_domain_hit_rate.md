# 获取域名命中率-GetNewUcdnDomainHitRate

获取域名命中率

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Type|int|时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天的粒度）|**Yes**|
|DomainId.n|string|域名id，创建域名时生成的id。默认全部域名|No|
|Areacode|string|查询带宽区域 cn代表国内 abroad代表海外，只支持国内|No|
|BeginTime|int|查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。如没有赋值，则返回缺少参 数错误，如果没有EndTime，BeginTime也可以不赋值，EndTime默认当前时间，BeginTime 默认前一天的当前时间。|No|
|EndTime|int|查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|HitRateList|array|请求数实例表。|No|

## HitRateInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|带宽获取的时间点。格式：时间戳|No|
|FlowHitRate|float|流量命中率，单位%|No|
|RequestHitRate|float|请求数命中率，单位%|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetNewUcdnDomainHitRate
&DomainId.n=kdINXUac
&Areacode=OvvqAfwC
&BeginTime=5
&EndTime=1
&Type=9
```

# Response Example
```
{
    "Action": "GetNewUcdnDomainHitRateResponse", 
    "RequestList": [
        {
            "OriginRequest": 4, 
            "CdnRequest": 8, 
            "Time": 6
        }, 
        {
            "OriginRequest": 1, 
            "CdnRequest": 2, 
            "Time": 4
        }, 
        {
            "OriginRequest": 2, 
            "CdnRequest": 6, 
            "Time": 1
        }, 
        {
            "OriginRequest": 9, 
            "CdnRequest": 2, 
            "Time": 9
        }, 
        {
            "OriginRequest": 1, 
            "CdnRequest": 1, 
            "Time": 7
        }, 
        {
            "OriginRequest": 6, 
            "CdnRequest": 4, 
            "Time": 8
        }, 
        {
            "OriginRequest": 8, 
            "CdnRequest": 3, 
            "Time": 8
        }
    ], 
    "RetCode": 0
}
```

