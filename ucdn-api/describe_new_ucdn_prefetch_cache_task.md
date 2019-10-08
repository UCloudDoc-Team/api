# 获取预取任务状态-DescribeNewUcdnPrefetchCacheTask

获取预取任务状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|TaskId.n|string|提交任务时返回的任务ID|No|
|BeginTime|int|查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值|No|
|EndTime|int|查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。|No|
|Status|string|需要获取的内容预热的状态，枚举值：success：成功；wait：等待处理；process：正在处理；failure：失败； unknow：未知，默认选择所有状态|No|
|Offset|int|数据偏移量，默认为0，自然数|No|
|Limit|int|返回数据长度,默认全部，自然数|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|预热任务的总数|No|
|TaskList|array|预热任务信息，参考TaskInfo|No|

## TaskInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeNewUcdnPrefetchCacheTask
&ProjectId=xxxxx
&TaskId.0=feTvWytY
&BeginTime=2
&EndTime=3
&Status=uwNWouHX
&Offset=1
&Limit=1
```

# Response Example
```
{
    "Action": "DescribeNewUcdnPrefetchCacheTaskResponse", 
    "TotalCount": 4, 
    "TaskList": [
        {
            "Status": "ySoPLGgE", 
            "UrlLists": [
                {
                    "Url": "xChNHhYo", 
                    "FinishTime": 1, 
                    "Status": "pmUWBVxw", 
                    "CreateTime": 6, 
                    "Progress": 3
                }, 
                {
                    "Url": "lKGDMDQq", 
                    "FinishTime": 7, 
                    "Status": "xCZMvZWZ", 
                    "CreateTime": 3, 
                    "Progress": 7
                }, 
                {
                    "Url": "ptLqMQuh", 
                    "FinishTime": 9, 
                    "Status": "zMxmxYcf", 
                    "CreateTime": 6, 
                    "Progress": 9
                }, 
                {
                    "Url": "YhpEnOmI", 
                    "FinishTime": 1, 
                    "Status": "OaxNseKe", 
                    "CreateTime": 4, 
                    "Progress": 4
                }, 
                {
                    "Url": "PEBgMeNh", 
                    "FinishTime": 5, 
                    "Status": "etAmHzPP", 
                    "CreateTime": 4, 
                    "Progress": 4
                }
            ], 
            "CreateTime": 4, 
            "TaskId": "mEuMcQSL"
        }, 
        {
            "Status": "JKrNCisb", 
            "UrlLists": [
                {
                    "Url": "XqHsIOtd", 
                    "FinishTime": 2, 
                    "Status": "XynKYAiJ", 
                    "CreateTime": 3, 
                    "Progress": 6
                }, 
                {
                    "Url": "EYRxaYAM", 
                    "FinishTime": 6, 
                    "Status": "rCoGJtmC", 
                    "CreateTime": 1, 
                    "Progress": 3
                }, 
                {
                    "Url": "ehwfbnDN", 
                    "FinishTime": 6, 
                    "Status": "sFsEYOgd", 
                    "CreateTime": 5, 
                    "Progress": 2
                }, 
                {
                    "Url": "FxacwAet", 
                    "FinishTime": 5, 
                    "Status": "EwSSKJad", 
                    "CreateTime": 8, 
                    "Progress": 3
                }, 
                {
                    "Url": "VRJFzzlH", 
                    "FinishTime": 5, 
                    "Status": "SkdViYPP", 
                    "CreateTime": 8, 
                    "Progress": 7
                }, 
                {
                    "Url": "LwAewYSo", 
                    "FinishTime": 3, 
                    "Status": "hcAQXhoN", 
                    "CreateTime": 5, 
                    "Progress": 5
                }, 
                {
                    "Url": "eJpkSqiP", 
                    "FinishTime": 3, 
                    "Status": "AiVaeqAx", 
                    "CreateTime": 7, 
                    "Progress": 2
                }
            ], 
            "CreateTime": 1, 
            "TaskId": "mYtrUNKc"
        }, 
        {
            "Status": "dDQVOfuA", 
            "UrlLists": [
                {
                    "Url": "qKIoMLtR", 
                    "FinishTime": 5, 
                    "Status": "okiJCQZU", 
                    "CreateTime": 8, 
                    "Progress": 2
                }, 
                {
                    "Url": "fVxMWSUL", 
                    "FinishTime": 9, 
                    "Status": "SXVfOLXG", 
                    "CreateTime": 1, 
                    "Progress": 6
                }, 
                {
                    "Url": "UtBAuUmZ", 
                    "FinishTime": 4, 
                    "Status": "wOXhjduh", 
                    "CreateTime": 2, 
                    "Progress": 9
                }
            ], 
            "CreateTime": 7, 
            "TaskId": "ZJazzIIh"
        }, 
        {
            "Status": "LeqJkycM", 
            "UrlLists": [
                {
                    "Url": "oEqzcgMA", 
                    "FinishTime": 8, 
                    "Status": "YYcZbXWw", 
                    "CreateTime": 6, 
                    "Progress": 5
                }, 
                {
                    "Url": "UKXkiPDK", 
                    "FinishTime": 6, 
                    "Status": "HYZmwEUR", 
                    "CreateTime": 1, 
                    "Progress": 6
                }, 
                {
                    "Url": "aGCnxHXv", 
                    "FinishTime": 2, 
                    "Status": "FBCAWBMW", 
                    "CreateTime": 2, 
                    "Progress": 3
                }
            ], 
            "CreateTime": 3, 
            "TaskId": "sEiKGYYr"
        }, 
        {
            "Status": "GVWVbBkR", 
            "UrlLists": [
                {
                    "Url": "MmoeVMJQ", 
                    "FinishTime": 2, 
                    "Status": "iQguQPft", 
                    "CreateTime": 9, 
                    "Progress": 4
                }, 
                {
                    "Url": "YtzBfJQF", 
                    "FinishTime": 9, 
                    "Status": "CPqqNmqO", 
                    "CreateTime": 3, 
                    "Progress": 3
                }
            ], 
            "CreateTime": 1, 
            "TaskId": "ByScqGMr"
        }, 
        {
            "Status": "RPkHZOFJ", 
            "UrlLists": [
                {
                    "Url": "MPKzOnkG", 
                    "FinishTime": 2, 
                    "Status": "hfRtxJYA", 
                    "CreateTime": 5, 
                    "Progress": 8
                }, 
                {
                    "Url": "NqeqhcDn", 
                    "FinishTime": 2, 
                    "Status": "NOgImUxr", 
                    "CreateTime": 3, 
                    "Progress": 8
                }, 
                {
                    "Url": "dehdHOoC", 
                    "FinishTime": 5, 
                    "Status": "jadthNuI", 
                    "CreateTime": 5, 
                    "Progress": 8
                }, 
                {
                    "Url": "UxQiBarm", 
                    "FinishTime": 5, 
                    "Status": "KCTmUkpl", 
                    "CreateTime": 4, 
                    "Progress": 9
                }
            ], 
            "CreateTime": 5, 
            "TaskId": "sklDNgoJ"
        }, 
        {
            "Status": "xRRNKppD", 
            "UrlLists": [
                {
                    "Url": "fJbCCejm", 
                    "FinishTime": 5, 
                    "Status": "qhlDmXYg", 
                    "CreateTime": 8, 
                    "Progress": 3
                }, 
                {
                    "Url": "LkEYimIs", 
                    "FinishTime": 4, 
                    "Status": "IViYWdSq", 
                    "CreateTime": 8, 
                    "Progress": 4
                }, 
                {
                    "Url": "NbtQArje", 
                    "FinishTime": 1, 
                    "Status": "uCbnQqLo", 
                    "CreateTime": 2, 
                    "Progress": 7
                }, 
                {
                    "Url": "ylzrmbHW", 
                    "FinishTime": 7, 
                    "Status": "SHEYNyGf", 
                    "CreateTime": 7, 
                    "Progress": 9
                }, 
                {
                    "Url": "cYVWknQE", 
                    "FinishTime": 9, 
                    "Status": "lgCecoFw", 
                    "CreateTime": 3, 
                    "Progress": 8
                }, 
                {
                    "Url": "OEykZxWV", 
                    "FinishTime": 7, 
                    "Status": "JhdorWII", 
                    "CreateTime": 4, 
                    "Progress": 1
                }, 
                {
                    "Url": "RWWfGzMi", 
                    "FinishTime": 4, 
                    "Status": "GlHxqIgx", 
                    "CreateTime": 4, 
                    "Progress": 1
                }
            ], 
            "CreateTime": 3, 
            "TaskId": "YLQhYqyq"
        }
    ], 
    "RetCode": 0, 
    "Test": "ryEuYMgQ"
}
```

