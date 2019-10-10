# 获取转码任务列表-GetCodecTaskList

获取转码任务列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BeginTime|int|查询的开始时间，单位：unix时间戳。如果不传，若没有传结束时间，则为当前时间的前七天。否则为结束时间的前七天。|No|
|EndTime|int|查询的结束时间，单位：unix时间戳。如果不传，若没有传开始时间，则为当前时间，否则为开始时间的后七天。EndTime必须为当前时间往前一个月内，也就是支持一个月内的任务查询。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TaskList|array|任务信息列表|No|

## CodecPattenInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TaskId|string|任务ID|**Yes**|
|SrcUrl|string|原始视频url地址|**Yes**|
|DestVideoName|string|输出文件名|**Yes**|
|DestBucket|string|输出文件的存储空间|**Yes**|
|DestFormat|string|输出视频封装格式|**Yes**|
|Duration|int|视频时长，单位：秒。只有当任务状态为处理完成时，该参数有意义，其他状态该参数为0。|**Yes**|
|CodecLevel|string|转码清晰度：superdefinition、highdefinition、mediumdefinition、lowdefinition，分别对应计费的4种规格。只有当任务状态为处理完成时，该参数有意义，其他状态该参数为空字符串。|**Yes**|
|CreateTime|string|任务创建时间，单位：Unix时间戳|**Yes**|
|Status|string|任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetCodecTaskList
```

# Response Example
```
{
    "Action": "GetCodecTaskListResponse", 
    "TaskList": [
        {
            "Status": "finished", 
            "DestBucket": "video.cn-bj.ufileos.com", 
            "DestVideoName": "myvideo_hd.mp4", 
            "SrcUrl": "http://video.ucloud.cn/myvideo.mp4", 
            "CreateTime ": 1496359861, 
            "TaskId": "1", 
            "DestFormat": "mp4", 
            "Duration": 155, 
            "CodecLevel": "superdefinition"
        }
    ], 
    "RetCode": 0
}
```

