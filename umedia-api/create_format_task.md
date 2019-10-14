# 创建封装任务-CreateFormatTask

创建封装任务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Url.n|string|原始视频地址，只支持http协议，不支持https以及其他协议。单次提交url数量最多为10条。|**Yes**|
|DestBucket|string|存放转码后视频文件的bucket，需使用bucket全名，如：video.cn-bj.ufileos.com|**Yes**|
|BaseDir|string|上传文件的路径。DestBucket、BaseDir、目标文件名三个参数共同决定了转码后文件的下载url地址。|No|
|DestFormat|string|目标文件的封装格式，支持mp4、flv、mpegts、m3u8四种。不传该参数，则默认为m3u8|No|
|CallbackUrl|string|任务结束后，回调客户的url地址。|No|
|VideoBeginTime|int|视频的开始时间,时间单位为秒|No|
|VideoEndTime|int|视频的结束时间,时间单位为秒|No|

?> 视频转码、截图、鉴黄等处理完成后， UMedia 可以回调用户的接口， 通知处理的结果。
客户需提供一个接收处理结果的 api 接口，处理结果被封装成 json 字符串，通过 POST 请求，
传递给用户的接口。具体回调参数字段如下：

切片回调详细参数
{
"retcode":0, //0 表示处理成功，
"task_id":"1", //提交转码生成的任务 id
"src_url":"http://src.ufile.ucloud.cn/my.mp4", //原始 url 地址
"dest_video_name":"my.m3u8", //目标文件名
"dest_video_url":"http://dest.ufile.ucloud.cn/my.m3u8", //目标文件地址
"duration":587, //切片后视频的时长，单位秒
"message":"succ" //处理结果描述
}

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalTaskCount|int|生成的总的任务条数|No|
|TaskIdList|array|生成的任务Id列表|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateFormatTask
&Url.0=https://video.ufile.ucloud.cn/myvideo.mp4
&DestFormat=mp4
&DestBucket=video.cn-bj.ufileos.com
```

# Response Example
```
{
    "Action": "CreateFormatTaskResponse", 
    "TaskIdList": [
        {
            "TaskId": "3387"
        }
    ], 
    "TotalTaskCount": 1, 
    "RetCode": 0
}
```

