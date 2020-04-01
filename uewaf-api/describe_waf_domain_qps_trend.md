# 查询waf域名QPS趋势-DescribeWafDomainQPSTrend

查询waf域名QPS趋势

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
|TimeStamp|string|时间戳|**Yes**|
|SrcQPS|string|到源站qps|**Yes**|
|WafQPS|string|到WAF的qps|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafDomainQPSTrend
&BeginTime=6
&EndTime=9
&Domain=YqXdyWQk
&ProjectId=7
&RecordId=4
```

# Response Example
```
{
    "Info": [
        "vZHzdylT", 
        "qXrQmnKn", 
        "IIPzHwNB", 
        "CAIGIGaL", 
        "QBftqmWu", 
        "qIClYsyE", 
        "KNgliVgp", 
        "VBceKBYe"
    ], 
    "Action": "DescribeWafDomainQPSTrendResponse", 
    "RetCode": 0
}
```

