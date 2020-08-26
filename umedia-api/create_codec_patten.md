# 创建转码模版 - CreateCodecPatten

## 简介

创建转码模版






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateCodecPatten)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCodecPatten`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **PattenName** | string | 模版名称,长度不查过256个字节 |**Yes**|
| **DestVideoBitrate** | int | 视频码率，单位kbps,范围[200,4000]或者是0。如果为0，则表示由视频工厂输出自适应码率 |**Yes**|
| **DestFormat** | string | 目标视频格式，可选值为mp4、flv、mpegts。 |**Yes**|
| **DestVideoResolution** | string | 视频分辨率，格式为像素宽度x像素高度，例如1280x720。不传该字段则表示不改变分辨率 |No|
| **DestAudioBitrate** | string | 音频码率，单位kbps，范围[16,192]，推荐使用48。 |No|
| **DestAudioSample** | int | 音频采样率，单位hz,可选值为22050、32000，44100，推荐使用44100。 |No|
| **DestAudioChannel** | int | 音频声道数量。可选值为1（单声道）、2（双声道），推荐使用2（双声道）。 |No|
| **DestSuffix** | string | 目标视频的文件名后缀，长度不超过32个字符 |No|
| **CallbackUrl** | string | 转码任务结束后，回调客户的url地址。 |No|
| **DestVideoCodec** | string | 视频的编码类型 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PattenId** | string | 创建成功后生成的转码模版ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCodecPatten
&PattenName=我的模版
&DestVideoBitrate=1200
&DestVideoResolution=1280x720
&DestAudioBitrate=48
&DestAudioSample=44100
&DestAudioChannel=2
&DestFormat=mp4
&DestSuffix=720p
```

### 响应示例
    
```json
{
  "Action": "CreateCodecPattenResponse",
  "PattenId": "123",
  "RetCode": 0
}
```





