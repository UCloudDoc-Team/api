# WAF下行流量趋势-StatWafTXTRend

WAF下行流量趋势

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BeginTime|int|开始时间，时间戳，单位：秒|**Yes**|
|EndTime|int|结束时间，时间戳，单位：秒|**Yes**|
|Method|string|min，avg，max，默认为‘max’|No|
|Domain|string|域名|No|
|Extent|int|统计区间，单位：秒，取值范围0-7200|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Result|array|下行流量统计信息|No|

## StatTXResult
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Count|int|返回节点个数|**Yes**|
|Unit|string|流量计量单位|**Yes**|
|Detail|array|下行流量详情数组|**Yes**|

## StatTXDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|string|时间戳|**Yes**|
|WafTX|int|waf下行流量|**Yes**|
|SrcTX|int|源站下行流量|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StatWafTXTRend
&ProjectId=dyGatQKk
&BeginTime=xasvfvf
&EndTime=cdncnvc
&Domain=cvvdvkj
&Method=avg
&RecordId=5
&Extent=3
```

# Response Example
```
{
    "Action": "StatWafTXTRendResponse", 
    "RetCode": 0
}
```

