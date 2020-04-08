# 获取WAF QPS趋势-StatWafQPSTrend

获取WAF QPS趋势

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
|Detail|array|QPS统计结果集合，参考QPSTrendDetail|**Yes**|

## QPSTrendDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|int|时间戳|**Yes**|
|SrcQPS|string|到源站qps|**Yes**|
|WafQPS|string|到WAF的qps|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StatWafQPSTrend
&ProjectId=org-xxx
&BeginTime=1586231349
&EndTime=1586231460
&Domain=www.test.com
&Method=min
```

# Response Example
```
{
    "Action": "StatWafQPSTrendResponse", 
    "RetCode": 0, 
    "Result": {
        "Count": 1, 
        "Type": "QPS", 
        "Detail": [
            {
                "Timestamp": 1586227440, 
                "WafQps": 1, 
                "SrcQps": 1
            }
        ]
    }
}
```

