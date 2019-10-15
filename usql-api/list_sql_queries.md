# 获取历史SQL查询列表-ListSQLQueries

获取用户提交过的历史SQL查询的列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|TotalCount|int|历史SQL查询总数|No|
|Queries|array|SQL查询集合|No|

## QuerySummary
|Parameter name|Type|Description|Required|
|---|---|---|---|
|QueryId|string|查询ID|No|
|QueryType|string|查询类型|No|
|QueryString|string|查询语句|No|
|State|string|查询状态|No|
|ScannedBytes|int|扫描字节数量|No|
|ErrorMessage|string|错误信息|No|
|ElapsedTimeMillis|int|查询耗时， 单位:：毫秒|No|
|StartTime|int|查询启动时间|No|
|EndTime|int|查询结束时间|No|

# Request Example
```
https://api.ucloud.cn/?Action=ListSQLQueries
&Region=cn-bj
&ProjectId=apUufFKW
```

# Response Example
```
{
    "Action": "ListSQLQueriesResponse", 
    "TotalCount": 124, 
    "Request": "c1ce7672-ffa9-4d70-b35c-ba53d066f9ce", 
    "RetCode": 0, 
    "Queries": [
        {
            "ScannedBytes": 0, 
            "ErrorMessage": "line 1:16: Catalog hive-hadoop2 does not exist", 
            "State": "FAILED", 
            "QueryId": "20180821_120614_00000_a2t8n", 
            "StartTime": "2018-08-21T12:06:14.000+0000", 
            "EndTime": "2018-08-21T12:06:16.000+0000"
        }, 
        {
            "ScannedBytes": 0, 
            "ErrorMessage": "line 1:15: Catalog hive-hadoop2 does not exist", 
            "State": "FAILED", 
            "QueryId": "20180830_133406_00000_223ex", 
            "StartTime": "2018-08-30T13:34:06.000+0000", 
            "EndTime": "2018-08-30T13:34:07.000+0000"
        }
    ]
}
```

