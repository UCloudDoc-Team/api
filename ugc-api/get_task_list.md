# 查询任务列表-GetTaskList

获取提交的任务列表。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|StartTime|int|时间检索起始时间|**Yes**|
|EndTime|int|时间检索结束时间|**Yes**|
|TaskId|string|任务ID，不填返回所有Id的任务|No|
|TaskName|string|任务名称，不填返回所有名称的任务|No|
|ImageName|string|任务运行对应的镜像名|No|
|TaskType|string|同步任务Sync，异步任务Async；默认为All|No|
|State|string|All:所有任务，Running：运行中，Success：成功，Fail：失败；默认为ALL|No|
|OrderBy|string|Default: 默认排序|No|
|Limit|int|返回数据长度，默认为20|No|
|Offset|int|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|如果发生错误为错误描述|No|
|TotalCount|int|满足条件的任务总数|No|
|TaskSet|array|JSON格式的任务列表 参数见 UgcTaskSet|No|

## UgcTaskSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TaskId|string|任务ID|No|
|TaskName|string|任务名称|No|
|TaskType|string|同步任务Sync，异步任务Async|No|
|Owner|string|任务创建者|No|
|State|string|Running：运行中，Success：成功，Fail：失败|No|
|CreateTime|int|创建时间，格式为Unix时间戳|No|
|StartTime|int|开始时间，格式为Unix时间戳|No|
|EndTime|int|结束时间，格式为Unix时间戳|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetTaskList
&Region=cn-bj2
```

# Response Example
```
{
    "Action": "GetTaskListResponse", 
    "TotalCount": 1, 
    "Message": "", 
    "RetCode": 0, 
    "TaskSet": [
        {
            "TaskId": "0b560b1d-f3b1-43de-a492-08875d79211b", 
            "State": "Success", 
            "StartTime": 1234567892, 
            "Owner": "ucs", 
            "TaskName": "ucs-helloworld", 
            "EndTime": 1234567990, 
            "CreateTime": 1234567890
        }
    ]
}
```

