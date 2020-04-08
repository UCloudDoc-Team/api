# 获取WAF请求数趋势-StatWafReqsTrend

获取WAF请求数趋势

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BeginTime|int|起始时间戳,单位 秒|**Yes**|
|EndTime|int|终止时间戳,单位 秒|**Yes**|
|Domain|string|如果查看指定域名的统计信息,传入域名,否则不传该参数,或者传空字符串|No|
|Extent|int|统计区间，单位：秒，取值范围0-7200|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Result|object|请求数趋势统计结果，参考StatReqsResult|No|

## StatReqsResult
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Count|int|返回节点个数|**Yes**|
|Detail|array|请求数统计详细信息列表，参考StatReqsDetail|**Yes**|

## StatReqsDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|int|时间戳|**Yes**|
|Reqs|int|请求总数|**Yes**|
|ClientErr|int|客户端错误数|**Yes**|
|ServerErr|int|服务端错误数|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StatWafReqsTrend
&Extent=org-xxx
&BeginTime=1586231349
&EndTime=1586231408
&Domain=www.test.com
```

# Response Example
```
{
    "Action": "StatWafReqsTrendResponse", 
    "RetCode": 0, 
    "Result": {
        "Count": 61, 
        "Type": "Reqs", 
        "Detail": [
            {
                "Timestamp": 1586231350, 
                "ServerErr": 0, 
                "ClientErr": 0, 
                "Reqs": 11
            }
        ]
    }
}
```

