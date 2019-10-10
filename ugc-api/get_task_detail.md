# 查看任务详情-GetTaskDetail

查看任务详情。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|TaskId|string|任务ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageName|string|任务使用的镜像名|No|
|Cmd|string|镜像运行参数|No|
|OutputDir|string|输出文件目录|No|
|OutputFileName|string|输出文件名称|No|
|TaskId|string|任务ID|No|
|TaskName|string|任务名称|No|
|TaskType|string|同步任务Sync，异步任务Async|No|
|Owner|string|任务创建者|No|
|State|string|Running：运行中，Success：成功，Fail：失败|No|
|CreateTime|int|创建时间，格式为Unix时间戳|No|
|StartTime|int|开始时间，格式为Unix时间戳|No|
|EndTime|int|结束时间，格式为Unix时间戳|No|
|Timeout|int|超时时间|No|
|StdoutBrief|string|任务标准输出概要|No|
|StderrBrief|string|任务标准错误概要|No|
|CPUUsage|int|CPU使用情况|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetTaskDetail
&Region=cn-bj2
&TaskId=123456
```

# Response Example
```
{
    "EndTime": 1234567892, 
    "RetCode": 0, 
    "StderrBrief": "", 
    "CPUUsage": 10, 
    "Cmd": "", 
    "StdoutBrief": "hello world", 
    "OutputFileName": "result", 
    "CreateTime": 1234567892, 
    "Owner": "ucs", 
    "State": "Success", 
    "ImageName": "ucsdr.ucloud.cn:5000/ucs/helloworld:6", 
    "Timeout": 10, 
    "TaskId": "12345", 
    "TaskType": "Sync", 
    "Action": "GetTaskDetailResponse", 
    "Message": "", 
    "StartTime": 1234567892, 
    "TaskName": "Hello World Test", 
    "OutputDir": "tmp"
}
```

