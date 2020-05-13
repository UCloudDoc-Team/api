# 使用模版创建转码任务 - CreateCodecTaskByPatten

## 简介

使用模版创建转码任务

?> 视频转码、截图、鉴黄等处理完成后， UMedia 可以回调用户的接口， 通知处理的结果。<br />客户需提供一个接收处理结果的 api 接口，处理结果被封装成 json 字符串，通过 POST 请求，<br />传递给用户的接口。具体回调参数字段如下：<br />1）转码回调详细参数：<br />{<br />"retcode":0, //0 表示处理成功，<br />"task_id":"1", //提交转码生成的任务 id<br />"src_url":"http://src.ufile.ucloud.cn/my.mp4", //原始 url 地址<br />"dest_video_name":"my_720p.mp4", //目标文件名<br />"dest_video_url":"http://dest.ufile.ucloud.cn/my_720p.mp4", //目标文件地址<br />"duration":587, //转码后 视频的时长，单位秒<br />"file_size":587, //视频的文件大小<br />"width":1280, //视频的宽，单位为像素<br />"height":720, //视频的高，单位为像素<br />"message":"succ" //处理结果描述<br />}



## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateCodecTaskByPatten)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCodecTaskByPatten`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Url.N** | string | 原始视频地址，只支持http协议，不支持https以及其他协议。单次提交url数量最多为10条。 |**Yes**|
| **DestBucket** | string | 存放转码后视频文件的bucket，需使用bucket全名，如：video.cn-bj.ufileos.com |**Yes**|
| **CodecPattenId.N** | string | 转码模版Id，单次提交支持最多3个转码模版。下标相同的转码模版、水印模版、片头片尾模版进行组合。 |**Yes**|
| **BaseDir** | string | 上传到ufile上文件的路径 |No|
| **WatermarkPattenId** | string | 水印模版Id |No|
| **HeadTailPattenId** | string | 片头片尾模版Id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalTaskCount** | int | 生成的总的任务条数 |No|
| **TaskIdList** | array[[*TaskIdList*](#TaskIdList)] | 生成的任务Id列表 |No|

#### 数据模型


#### TaskIdList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | 任务ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCodecTaskByPatten
&Url.0=https://video.ufile.ucloud.cn/myvideo.mp4
&DestBucket=video.cn-bj.ufileos.com
&CodecPattenId.0=1
&CodecPattenId.1=4
&WaterMarkPattenId=1
```

### 响应示例
    
```json
{
  "Action": "CreateCodecTaskByPattenResponse",
  "RetCode": 0,
  "TaskIdList": [
    {
      "TaskId": "3386"
    },
    {
      "TaskId": "3387"
    }
  ],
  "TotalTaskCount": 2
}
```





