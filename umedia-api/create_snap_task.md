# 创建截图任务-CreateSnapTask

创建截图任务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Url.n|string|原始视频地址，只支持http协议，不支持https以及其他协议。单次提交url数量最多为10条。|**Yes**|
|SnapType|string|截图模式，single表示确定时间点单张截图，periodic表示周期截图, dynamic表示为gif截图|**Yes**|
|SnapTime|int|截图模式为single时表示截图时间点，periodic时表示时间间隔|**Yes**|
|DestBucket|string|存放转码后视频文件的bucket，需使用bucket全名，如：video.cn-bj.ufileos.com|**Yes**|
|ImageFormat|string|图片类型，支持jpg、png、gif|**Yes**|
|ImageSize|string|目标图片尺寸大小，格式为像素宽度x像素高度，例如1280x720。不传此参数则表示使用原始视频尺寸。|No|
|BaseDir|string|上传文件的路径。DestBucket、BaseDir、目标文件名三个参数共同决定了图片文件的下载url地址。|No|
|CallbackUrl|string|任务结束后，回调客户的url地址。|No|
|GifFrameRate|float|Gif图片的播放速度，单位为帧/秒|No|

```
视频转码、截图、鉴黄等处理完成后， UMedia 可以回调用户的接口， 通知处理的结果。
客户需提供一个接收处理结果的 api 接口，处理结果被封装成 json 字符串，通过 POST 请求，
传递给用户的接口。具体回调参数字段如下：

截图回调详细参数：
{
"retcode":0, //0 表示处理成功，
"task_id":"1", //提交截图生成的任务 id
"src_url":"http://src.ufile.ucloud.cn/my.mp4", //原始 url 地址
"image_count":3, //截图张数
"image_list":[
{"image_url":"http://dest.ufile.ucloud.cn/my_1.jpg"},
{"image_url":"http:// dest.ufile.ucloud.cn/my_2.jpg"},
{"image_url":"http://dest.ufile.ucloud.cn/my_3.jpg"}
],
"message":"succ" //处理结果描述
}
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalTaskCount|int|生成的总的任务条数|No|
|TaskIdList|array|生成的任务Id列表|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateSnapTask
&Url.0=https://video.ufile.ucloud.cn/myvideo.mp4
&SnapType=single
&SnapTime=10
&ImageFormat=jpg
&DestBucket=video.cn-bj.ufileos.com
```

# Response Example
```
{
    "Action": "CreateSnapTaskResponse", 
    "TaskIdList": [
        {
            "TaskId": "3387"
        }
    ], 
    "TotalTaskCount": 1, 
    "RetCode": 0
}
```

