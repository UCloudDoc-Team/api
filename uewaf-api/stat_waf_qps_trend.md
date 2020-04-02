# UEWAFQPS趋势-StatWafQPSTrend

UEWAF QPS趋势

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，不填表示默认项目|No|
|BeginTime|int|起始时间戳,单位：秒|**Yes**|
|EndTime|int|终止时间戳,单位：秒|**Yes**|
|Method|string|取点方式max\|min\|avg,默认取平均值avg|No|
|Domain|string|要过滤的域名,统计所有域名时不传该参数或者传空字符串|No|
|Extent|int|统计区间，单位：秒，取值范围0-7200|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Detail|object|QPS趋势流量统计结果，参考QPSStatResult|No|

## QPSStatResult
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Count|int|采样点个数|**Yes**|
|Detail|array|QPS统计结果集合|**Yes**|

## QPSTrendDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|string|时间戳|**Yes**|
|SrcQPS|string|到源站qps|**Yes**|
|WafQPS|string|到WAF的qps|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StatWafQPSTrend
&BeginTime=5
&EndTime=3
&Method=min
&Domain=NDDBqcvc
&Extent=2
```

# Response Example
```
{
    "Action": "StatWafQPSTrendResponse", 
    "Count": 5, 
    "Type": "MElGoXZr", 
    "RetCode": 0
}
```

