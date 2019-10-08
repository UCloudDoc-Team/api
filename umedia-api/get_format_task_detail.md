# 获取封装任务详情-GetFormatTaskDetail

获取封装任务详情

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|TaskId|string|查询的截图任务ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SrcUrl|string|原始视频url地址|No|
|DestVideoName|string|输出视频文件名|No|
|DestVideoFormat|string|输出视频封装格式|No|
|Duration|int|视频时长|No|
|DestBucket|string|存储图片的ufile的bucket名称|No|
|CreateTime|int|任务创建时间，单位：Unix时间戳|No|
|FinishTime|int|任务结束时间，单位：Unix时间戳。只有任务状态为处理完成时值才有意义，默认为0。|No|
|Status|string|任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetFormatTaskDetail&TaskId=1
```

# Response Example
```
{
    "FinishTime": 1496298900, 
    "Status": "finished", 
    "DestVideoName ": "myvideo.m3u8", 
    "DestBucket": "video.cn-bj.ufileos.com", 
    "RetCode": 0, 
    "DestVideoFortmat": "m3u8", 
    "SrcUrl": "http://video.ucloud.cn/myvideo.mp4", 
    "TaskId": "1", 
    "Action": "GetFormatTaskDetailResponse", 
    "CreateTime": 1496298697
}
```

