# 获取域名刷新任务状态-DescribeNewUcdnRefreshCacheTask

获取域名刷新任务状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|TaskId.n|string|提交任务时返回的任务ID|No|
|BeginTime|int|查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值|No|
|EndTime|int|查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。|No|
|Status|string|需要获取的内容刷新的状态，枚举值：success：成功；wait：等待处理；process：正在处理；failure：失败； unknow：未知，默认选择所有状态|No|
|Offset|int|数据偏移量，默认为0，自然数|No|
|Limit|int|返回数据长度,默认全部，自然数|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|刷新任务的总数|No|
|TaskList|array|刷新任务信息，参考TaskInfo|No|

## TaskInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeNewUcdnRefreshCacheTask
&ProjectId=xxxxxx
&TaskId.n=sHemHKgw
&BeginTime=2
&EndTime=6
&Status=JNhEgMiG
&Offset=3
&Limit=9
```

# Response Example
```
{
    "Action": "DescribeNewUcdnRefreshCacheTaskResponse", 
    "TotalCount": 2, 
    "TaskList": [
        {
            "Status": "success", 
            "UrlLists": [
                {
                    "Url": "http://xxxxx/test2.jpg", 
                    "FinishTime": 1548051103, 
                    "Progress": 100, 
                    "CreateTime": 1548051097, 
                    "Status": "success"
                }, 
                {
                    "Url": "http://xxxxx/test.jpg", 
                    "FinishTime": 1548051103, 
                    "Progress": 100, 
                    "CreateTime": 1548051097, 
                    "Status": "success"
                }
            ], 
            "Type": "file", 
            "CreateTime": 1548051097, 
            "TaskId": "20190121141137_4d8031d5"
        }
    ], 
    "RetCode": 0
}
```

