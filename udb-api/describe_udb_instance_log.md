# 获取UDB错误日志或慢查询日志-DescribeUDBInstanceLog

查询某一段时间内UDB的错误日志或慢查询日志

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|实例ID|**Yes**|
|BeginTime|int|查询的日志开始的时间戳（Unix Timestamp）。对于实时查询，这个参数应该是上次轮询请求时的时间戳，后台会返回从该值到当前时间的日志内容。|**Yes**|
|EndTime|int|查询日志的结束时间戳(Unix Timestamp），对于实时查询不传该值，与BeginTime的差值不超过24小时：(EndTime-BeginTime) < 24*60*60|**Yes**|
|LogType|string|查询日志的类型|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Log|string|查询到的日志内容，一段纯文本|No|
|NextTime|string|此次查询到的日志的下一个时间，用于下一次轮询时的BeginTime参数；如果日志查询结束则返回为空，前端结束查询|No|

# Request Example
```
http://api.ucloud.cn/?Action=DescribeUDBInstanceLog
&DBId=xxxxx
&BeginTime=1497262210
&EndTime=1497323400
&LogType=error
```

# Response Example
```
{
    "Action": "DescribeUDBInstanceLogResponse", 
    "NextTime": "1497323401", 
    "RetCode": 0, 
    "Log": ""
}
```

