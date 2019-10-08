# 获取截图任务列表-GetSnapTaskList

获取截图任务列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|BeginTime|int|查询的开始时间，单位：unix时间戳。如果不传，若没有传结束时间，则为当前时间的前七天。否则为结束时间的前七天。|No|
|EndTime|int|查询的结束时间，单位：unix时间戳。如果不传，若没有传开始时间，则为当前时间，否则为开始时间的后七天。EndTime必须为当前时间往前一个月内，也就是支持一个月内的任务查询。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TaskList|array|任务列表|No|

## SnapTaskInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TaskId|string|任务ID|**Yes**|
|SrcUrl|string|原始视频url地址|**Yes**|
|SnapType|string|截图模式，single表示确定时间点单张截图，periodic表示周期截图,dynamic表示为gif截图|**Yes**|
|ImageName|string|截图输出的文件名。对于周期截图，该字段表示不加后缀的文件名。|**Yes**|
|ImageFormat|string|图片格式类型|**Yes**|
|ImageCount|int|截图张数|**Yes**|
|CreateTime|int|任务创建时间，单位：Unix时间戳|No|
|Status|string|任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetSnapTaskList
```

# Response Example
```
{
    "Action": "GetSnapTaskListResponse", 
    "TaskList": [
        {
            "Status": "finished", 
            "TaskId": "1", 
            "SrcUrl": "http://video.ucloud.cn/myvideo.mp4", 
            "ImageName": "myvideo.jpg", 
            "ImageFormat ": "jpg", 
            "SnapType": "periodic", 
            "CreateTime": 1496298697, 
            "ImageCount": 5
        }
    ], 
    "RetCode": 0
}
```

