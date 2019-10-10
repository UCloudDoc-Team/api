# 清除日志-ClearUDBLog

清除UDB实例的log

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|DB实例的id,该值可以通过DescribeUDBInstance获取|**Yes**|
|LogType|int|日志类型，10-error（暂不支持）、20-slow（暂不支持 ）、30-binlog|**Yes**|
|BeforeTime|int|删除时间点(至少前一天)之前log，采用时间戳(秒)，默认当 前时间点前一天|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ClearUDBLog
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
&LogType=30    
```

# Response Example
```
{
    "Action": "ClearUDBLogResponse", 
    "RetCode": 0
}
```

