# 获取SQL查询详细信息-GetSQLQuery

获取用户提交的SQL查询任务的详细信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|QueryId|string|SQL查询的ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|QueryId|string|SQL查询ID|No|
|State|string|查询任务当前状态。RUNNING： 正在运行，CANCELLED：用户取消任务，SUCCEED：任务运行成功，FAILED： 任务运行失败|No|
|ElapsedTime|int|查询已运行时间|No|
|ScannedBytes|int|查询扫描数据字节数|No|
|QueryErrorCode|int|查询任务错误码|No|
|QueryErrorMessage|string|查询任务错误信息|No|
|StartTime|int|查询任务启动时间|No|
|EndTime|int|查询任务结束时间|No|
|Headers|array|查询结果字段名列表|No|
|QueryType|string|SQL查询类型， 有SELECT，CREATE_DATABASE, DROP_DATABASE, CREATE_TABLE, DROP_TABLE, SHOW_CREATE_TABLE|No|
|OutputRecordCount|int|查询结果的记录总数|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetSQLQuery
&Region=pre
&QueryId=20180913_082139_00000_22dwf
&ProjectId=iRdAMxGy
```

# Response Example
```
{
    "QueryErrorMessage": "", 
    "EndTime": "2018-09-13T08:21:42.000+0000", 
    "RetCode": 0, 
    "OutputRecordCount": 5, 
    "ScannedBytes": 2222, 
    "Request": "dfa59d02-ae37-4386-80d4-686a3c3fa021", 
    "ElapsedTime": 2363, 
    "Headers": [
        "n_nationkey", 
        "n_name", 
        "n_regionkey", 
        "n_comment"
    ], 
    "State": "SUCCEED", 
    "QueryId": "20180913_082139_00000_22dwf", 
    "StartTime": "2018-09-13T08:21:39.000+0000", 
    "Action": "GetSQLQueryResponse", 
    "QueryErrorCode": 0, 
    "QueryType": "fzWjVtIK"
}
```

