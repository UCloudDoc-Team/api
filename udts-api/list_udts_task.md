# 获取 Task 列表信息-ListUDTSTask

获取用户创建的 Task 信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Offset|string|偏移量，默认为 0|No|
|Limit|string|请求数量，默认为 20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息|**Yes**|
|Data|array|ListDataItem 数组|**Yes**|

## ListDataItem
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TaskId|string|任务 ID|No|
|Name|string|任务名称|No|
|Type|string|任务类型, full全量, incremental增量，full+incremental全量+增量。|No|
|MaxRetryCount|int|最大失败重试次数|No|
|CurRetryCount|int|当前失败重试次数|No|
|Status|string|任务状态|No|
|CreateTime|int|创建时间|No|
|Progress|object|全量迁移进度信息，增量迁移时为空 |No|

## Progress
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TotalCount|int|总条目数|No|
|CurCount|int|已迁移条目数|No|
|TotalDuration|int|估算总耗时间（单位秒）|No|
|CurDuration|int|已耗时间（单位秒）|No|
|Percentage|float|完成进度|No|

# Request Example
```
https://api.ucloud.cn/?Action=ListUDTSTask
&Region=cn-zj
&Page=1
&PageSize=1
&ProjectId=sUnUOVii
```

# Response Example
```
{
    "Action": "ListUDTSTaskResponse", 
    "Message": "zmbStUpW", 
    "Data": [
        "NiavATSz"
    ], 
    "RetCode": 0
}
```

