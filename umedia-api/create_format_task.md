# 创建封装任务 - CreateFormatTask

## 简介

创建封装任务

?> 视频转码、截图、鉴黄等处理完成后， UMedia 可以回调用户的接口， 通知处理的结果。<br />客户需提供一个接收处理结果的 api 接口，处理结果被封装成 json 字符串，通过 POST 请求，<br />传递给用户的接口。具体回调参数字段如下：<br /><br />切片回调详细参数<br />{<br />"retcode":0, //0 表示处理成功，<br />"task_id":"1", //提交转码生成的任务 id<br />"src_url":"http://src.ufile.ucloud.cn/my.mp4", //原始 url 地址<br />"dest_video_name":"my.m3u8", //目标文件名<br />"dest_video_url":"http://dest.ufile.ucloud.cn/my.m3u8", //目标文件地址<br />"duration":587, //切片后视频的时长，单位秒<br />"message":"succ" //处理结果描述<br />}




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateFormatTask)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateFormatTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Url.N** | string | 原始视频地址，只支持http协议，不支持https以及其他协议。单次提交url数量最多为10条。 |**Yes**|
| **DestBucket** | string | 存放转码后视频文件的bucket，需使用bucket全名，如：video.cn-bj.ufileos.com |**Yes**|
| **BaseDir** | string | 上传文件的路径。DestBucket、BaseDir、目标文件名三个参数共同决定了转码后文件的下载url地址。 |No|
| **DestFormat** | string | 目标文件的封装格式，支持mp4、flv、mpegts、m3u8四种。不传该参数，则默认为m3u8 |No|
| **CallbackUrl** | string | 任务结束后，回调客户的url地址。 |No|
| **VideoBeginTime** | int | 视频的开始时间,时间单位为秒 |No|
| **VideoEndTime** | int | 视频的结束时间,时间单位为秒 |No|

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
https://api.ucloud.cn/?Action=CreateFormatTask
&Url.0=https://video.ufile.ucloud.cn/myvideo.mp4
&DestFormat=mp4
&DestBucket=video.cn-bj.ufileos.com
```

### 响应示例
    
```json
{
  "Action": "CreateFormatTaskResponse",
  "RetCode": 0,
  "TaskIdList": [
    {
      "TaskId": "3387"
    }
  ],
  "TotalTaskCount": 1
}
```





