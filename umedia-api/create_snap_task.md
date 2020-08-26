# 创建截图任务 - CreateSnapTask

## 简介

创建截图任务

?> 视频转码、截图、鉴黄等处理完成后， UMedia 可以回调用户的接口， 通知处理的结果。<br />客户需提供一个接收处理结果的 api 接口，处理结果被封装成 json 字符串，通过 POST 请求，<br />传递给用户的接口。具体回调参数字段如下：<br /><br />截图回调详细参数：<br />{<br />"retcode":0, //0 表示处理成功，<br />"task_id":"1", //提交截图生成的任务 id<br />"src_url":"http://src.ufile.ucloud.cn/my.mp4", //原始 url 地址<br />"image_count":3, //截图张数<br />"image_list":[<br />{"image_url":"http://dest.ufile.ucloud.cn/my_1.jpg"},<br />{"image_url":"http:// dest.ufile.ucloud.cn/my_2.jpg"},<br />{"image_url":"http://dest.ufile.ucloud.cn/my_3.jpg"}<br />],<br />"message":"succ" //处理结果描述<br />}




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateSnapTask)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateSnapTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Url.N** | string | 原始视频地址，只支持http协议，不支持https以及其他协议。单次提交url数量最多为10条。 |**Yes**|
| **SnapType** | string | 截图模式，single表示确定时间点单张截图，periodic表示周期截图, dynamic表示为gif截图 |**Yes**|
| **SnapTime** | int | 截图模式为single时表示截图时间点，periodic时表示时间间隔 |**Yes**|
| **DestBucket** | string | 存放转码后视频文件的bucket，需使用bucket全名，如：video.cn-bj.ufileos.com |**Yes**|
| **ImageFormat** | string | 图片类型，支持jpg、png、gif |**Yes**|
| **ImageSize** | string | 目标图片尺寸大小，格式为像素宽度x像素高度，例如1280x720。不传此参数则表示使用原始视频尺寸。 |No|
| **BaseDir** | string | 上传文件的路径。DestBucket、BaseDir、目标文件名三个参数共同决定了图片文件的下载url地址。 |No|
| **CallbackUrl** | string | 任务结束后，回调客户的url地址。 |No|
| **GifFrameRate** | float | Gif图片的播放速度，单位为帧/秒 |No|

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
https://api.ucloud.cn/?Action=CreateSnapTask
&Url.0=https://video.ufile.ucloud.cn/myvideo.mp4
&SnapType=single
&SnapTime=10
&ImageFormat=jpg
&DestBucket=video.cn-bj.ufileos.com
```

### 响应示例
    
```json
{
  "Action": "CreateSnapTaskResponse",
  "RetCode": 0,
  "TaskIdList": [
    {
      "TaskId": "3387"
    }
  ],
  "TotalTaskCount": 1
}
```





