# UEWAF上行流量趋势-StatWafRXTrend

UEWAF上行流量趋势

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BeginTime|int|开始时间，时间错，单位：秒|**Yes**|
|EndTime|int|结束时间，时间戳，单位：秒|**Yes**|
|Domain|string|域名|No|
|Method|string|min,avg,max,默认为max|No|
|Extent|int|统计区间，单位：秒，取值范围0-7200|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Result|array|上行流量趋势统计结果|No|

## StatRXResult
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Count|int|返回节点个数|**Yes**|
|Uint|string|流量计量单位|**Yes**|
|Detail|array|上行流量详情|No|

## StatRXDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Timestamp|int|时间戳|**Yes**|
|WafRX|int|waf上行流量|**Yes**|
|SrcRX|int|源站上行流量|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StatWafRXTrend
&ProjectId=eIiJeNXx
&BeginTime=xasvfvf
&EndTime=cdncnvc
&Domain=cvvdvkj
&Method=avg
&Extent=9
```

# Response Example
```
{
    "Action": "StatWafRXTrendResponse", 
    "RetCode": 0
}
```

