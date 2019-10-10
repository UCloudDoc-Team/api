# 获取回源带宽数据（按时间分类）-GetUcdnPassBandwidth

获取回源带宽数据（cdn回客户源站部分）

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
|BandwidthDetail|array|回源带宽数据|No|

## BandwidthInfoDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|宽获取的时间点。格式：时间戳|**Yes**|
|Bandwidth|double|返回值带宽值数据。|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetUcdnPassBandwidth
&ProjectId=uFxeLekv
&Type=4
&DomainId.n=EFBocqQR
&Areacode=ZWFUlCEE
&BeginTime=9
&EndTime=1
```

# Response Example
```
{
    "Action": "GetUcdnPassBandwidthResponse", 
    "RetCode": 0, 
    "BandwidthDetail": [
        {
            "Bandwidth": 5.42314, 
            "Time": 1
        }
    ]
}
```

