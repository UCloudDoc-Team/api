# 获取域名状态码监控-GetNewUcdnDomainHttpCode

获取域名状态码监控

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
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
|HttpCodeDetail|array|状态码实例表。详细见HttpCodeInfo|No|

## HttpCodeInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|带宽获取的时间点。格式：时间戳|No|
|HttpOneXX|int|1xx数量|No|
|HttpTwoXX|int|2xx数量|No|
|HttpThreeXX|int|3xx数量|No|
|HttpFourXX|int|4xx数量|No|
|HttpFiveXX|int|5xx数量|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetNewUcdnDomainHttpCode
&Type=0
&DomainId.n=zWlrtaAE
&Areacode=cn
&BeginTime=7
&EndTime=9
&Type=9
```

# Response Example
```
{
    "Action": "GetNewUcdnDomainHttpCodeResponse", 
    "HttpCodeDetail": [
        {
            "HttpOneXX": 0, 
            "HttpTwoXX": 90, 
            "HttpFiveXX": 0, 
            "HttpThreeXX": 0, 
            "Time": 199632, 
            "HttpZeroXX": 7, 
            "HttpFourXX": 10
        }, 
        {
            "HttpOneXX": 0, 
            "HttpTwoXX": 90, 
            "HttpFiveXX": 0, 
            "HttpThreeXX": 0, 
            "Time": 199638, 
            "HttpZeroXX": 7, 
            "HttpFourXX": 10
        }
    ], 
    "RetCode": 0
}
```

