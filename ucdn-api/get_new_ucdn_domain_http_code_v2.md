# 获取域名详细状态码监控-GetNewUcdnDomainHttpCodeV2

获取域名详细状态码监控

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Type|int|时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天粒度，3表示按照一分钟粒度）|**Yes**|
|BeginTime|int|查询的起始时间，格式为Unix Timestamp。|**Yes**|
|EndTime|int|查询的结束时间，格式为Unix Timestamp。|**Yes**|
|DomainId.n|string|域名id，创建域名时生成的id。默认全部域名|No|
|Areacode|string|查询带宽区域 cn代表国内 abroad代表海外，只支持国内|No|

?> 详细状态码监控仅返回有数量的详细状态码，若无数量则不返回。

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|HttpCodeV2Detail|array|状态码详情|No|

## HttpCodeV2Detail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|时间|**Yes**|
|Http100|int|http100数量|No|
|Http101|int|http101数量|No|
|Http102|int|http102数量|No|
|Http200|int|http200数量|No|
|Http201|int|http201数量|No|
|Http202|int|http202数量|No|
|Http203|int|http203数量|No|
|Http204|int|http204数量|No|
|Http205|int|http205数量|No|
|Http206|int|http206数量|No|
|Http207|int|http207数量|No|
|Http300|int|http300数量|No|
|Http301|int|http301数量|No|
|Http302|int|http302数量|No|
|Http303|int|http303数量|No|
|Http304|int|http304数量|No|
|Http305|int|http305数量|No|
|Http306|int|http306数量|No|
|Http307|int|http307数量|No|
|Http400|int|http400数量|No|
|Http401|int|http401数量|No|
|Http402|int|http402数量|No|
|Http403|int|http403数量|No|
|Http404|int|http404数量|No|
|Http405|int|http405数量|No|
|Http406|int|http406数量|No|
|Http407|int|http407数量|No|
|Http408|int|http408数量|No|
|Http409|int|http409数量|No|
|Http410|int|http410数量|No|
|Http411|int|http411数量|No|
|Http412|int|http412数量|No|
|Http413|int|http413数量|No|
|Http414|int|http414数量|No|
|Http415|int|http415数量|No|
|Http416|int|http416数量|No|
|Http417|int|http417数量|No|
|Http418|int|http418数量|No|
|Http421|int|http421数量|No|
|Http422|int|http422数量|No|
|Http423|int|http423数量|No|
|Http424|int|http424数量|No|
|Http425|int|http425数量|No|
|Http426|int|http426数量|No|
|Http449|int|http449数量|No|
|Http451|int|http451数量|No|
|Http500|int|http500数量|No|
|Http501|int|http501数量|No|
|Http502|int|http502数量|No|
|Http503|int|http503数量|No|
|Http504|int|http504数量|No|
|Http505|int|http505数量|No|
|Http506|int|http506数量|No|
|Http507|int|http507数量|No|
|Http509|int|http509数量|No|
|Http510|int|http510数量|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetNewUcdnDomainHttpCodeV2
&ProjectId=wBkjkOLu
&Type=2
&DomainId.n=www.ucloud.cn
&Areacode=cn
&BeginTime=8
&EndTime=8
```

# Response Example
```
{
    "Action": "GetNewUcdnDomainHttpCodeV2Response", 
    "HttpCodeV2Detail": [
        {
            "Http206": 92972, 
            "Http200": 2137102581, 
            "Http304": 931756, 
            "Time": 1558443000, 
            "Http302": 5, 
            "Http412": 305, 
            "Http416": 74, 
            "Http404": 230669, 
            "Http500": 160
        }
    ], 
    "RetCode": 0
}
```

