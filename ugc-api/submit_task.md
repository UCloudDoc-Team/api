# 提交任务-SubmitTask

获取提交的任务列表，备注：该接口的Content-Type 应为application/octet-stream，传入数据以二进制数据流的形式POST发送。请求地址是api.ugc.service.ucloud.cn

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ImageName|string|任务使用的镜像名|**Yes**|
|AccessToken|string|授权Token	|**Yes**|
|Cmd|string|docker镜像运行参数	|No|
|OutputDir|string|算法输出的文件目录	|No|
|OutputFileName|string|算法输出的文件名称，支持输出到多个文件，如OutputFileName=output1&OutputFileName=output2|No|
|TaskType|string|同步任务Sync，异步任务Async，默认Async	|No|
|TimeOut|int|超时时间同步任务默认值为10秒，异步任务为默认为0，0表示不限制	|No|
|TaskName|string|任务名称	|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|错误描述|**Yes**|
|TaskId|string|任务ID(只有异步任务会返回该字段)|**Yes**|

# Request Example
```
http(s)://api.ugc.service.ucloud.cn/?Action=SubmitTask
&Region=cn-bj2
&ImageName=ucsdr.ucloud.cn:5000/ucs/helloworld:6
&OutputDir=/tmp
&OutputFileName=output
```

# Response Example
```
{
    "Action": "SubmitTaskResponse", 
    "Message": "wTbCqKAn", 
    "RetCode": 0, 
    "TaskId": "Wkxflnwp"
}
```

