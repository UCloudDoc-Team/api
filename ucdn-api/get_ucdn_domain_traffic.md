# 获取加速域名流量使用信息-GetUcdnDomainTraffic

获取加速域名流量使用信息

```
note
流量使用数据最长保留3个月的时间。
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DomainId.n|string|域名ID，创建加速域名时生成。默认全部域名|No|
|Areacode|string|查询流量区域 cn代表国内 abroad代表海外，默认全部区域。|No|
|BeginTime|int|查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。|No|
|EndTime|int|查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TrafficSet|array|流量实例表，具体结构见 UcdnDomainTrafficSet|No|

## UcdnDomainTrafficSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|流量获取的时间点，格式为Unix Timestamp|No|
|Value|float|查询每日流量总值，单位：GB|No|

# Request Example
```
http://api.ucloud.cn/?Action=GetUcdnDomainTraffic
&DomainId.0=ucdn-0331qd
&BeginTime=1420992000
&EndTime=1421166064
&Areacode=cn
```

# Response Example
```
{
    "Action": "GetUcdnDomainTrafficResponse", 
    "RetCode": 0, 
    " TrafficSet": [
        {
            "Value": 10.08, 
            "Time": " 1399305600"
        }, 
        {
            "Value": 10.08, 
            "Time": " 1399392000"
        }, 
        {
            "Value": 10.08, 
            "Time": " 1399392000"
        }
    ]
}
```

