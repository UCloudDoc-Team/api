# 查询WAF域名QPS趋势-DescribeWafDomainQPSTrend

查询WAF域名QPS趋势

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BeginTime|int|起始时间戳|**Yes**|
|EndTime|int|结束时间戳|**Yes**|
|Domain|string|域名|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Info|array|QPS信息，参考QPSTrendDetail|No|

## QPSTrendDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|int|时间戳|**Yes**|
|SrcQPS|string|到源站qps|**Yes**|
|WafQPS|string|到WAF的qps|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafDomainQPSTrend
&ProjectId=org-xxx
&BeginTime=1516204800
&EndTime=1516377600
```

# Response Example
```
{
    "Action": "DescribeWafDomainQPSTrendResponse", 
    "Info": {
        "Count": 1, 
        "Detail": [
            {
                "Timestamp": 1586227440, 
                "WafQps": 1, 
                "SrcQps": 1
            }
        ]
    }, 
    "RetCode": 0
}
```

