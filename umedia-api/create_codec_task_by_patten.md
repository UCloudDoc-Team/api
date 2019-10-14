# 使用模版创建转码任务-CreateCodecTaskByPatten

使用模版创建转码任务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Url.n|string|原始视频地址，只支持http协议，不支持https以及其他协议。单次提交url数量最多为10条。|**Yes**|
|DestBucket|string|存放转码后视频文件的bucket，需使用bucket全名，如：video.cn-bj.ufileos.com|**Yes**|
|CodecPattenId.n|string|转码模版Id，单次提交支持最多3个转码模版。下标相同的转码模版、水印模版、片头片尾模版进行组合。|**Yes**|
|BaseDir|string|上传到ufile上文件的路径|No|
|WatermarkPattenId|string|水印模版Id|No|
|HeadTailPattenId|string|片头片尾模版Id|No|

?> 视频转码、截图、鉴黄等处理完成后， UMedia 可以回调用户的接口， 通知处理的结果。
客户需提供一个接收处理结果的 api 接口，处理结果被封装成 json 字符串，通过 POST 请求，
传递给用户的接口。具体回调参数字段如下：
1）转码回调详细参数：
{
"retcode":0, //0 表示处理成功，
"task_id":"1", //提交转码生成的任务 id
"src_url":"http://src.ufile.ucloud.cn/my.mp4", //原始 url 地址
"dest_video_name":"my_720p.mp4", //目标文件名
"dest_video_url":"http://dest.ufile.ucloud.cn/my_720p.mp4", //目标文件地址
"duration":587, //转码后 视频的时长，单位秒
"file_size":587, //视频的文件大小
"width":1280, //视频的宽，单位为像素
"height":720, //视频的高，单位为像素
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
https://api.ucloud.cn/?Action=CreateCodecTaskByPatten
&Url.0=https://video.ufile.ucloud.cn/myvideo.mp4
&DestBucket=video.cn-bj.ufileos.com
&CodecPattenId.0=1
&CodecPattenId.1=4
&WaterMarkPattenId=1
```

# Response Example
```
{
    "Action": "CreateCodecTaskByPattenResponse", 
    "TaskIdList": [
        {
            "TaskId": "3386"
        }, 
        {
            "TaskId": "3387"
        }
    ], 
    "TotalTaskCount": 2, 
    "RetCode": 0
}
```

