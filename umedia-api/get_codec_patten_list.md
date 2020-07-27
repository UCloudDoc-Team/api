# 获取转码模版列表 - GetCodecPattenList

## 简介

获取转码模版列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCodecPattenList)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCodecPattenList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DefaultPattenList** | array[[*CodecPattenListNode*](#CodecPattenListNode)] | 系统预制的转码模版列表,详细结构见下表 |No|
| **CustomizedPattenList** | array[[*CodecPattenListNode*](#CodecPattenListNode)] | 客户定制的转码模版列表，详细结构见下表 |No|

#### 数据模型


#### CodecPattenListNode

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PattenId** | string | 模版的ID |**Yes**|
| **PattenName** | string | 模版名称,长度不查过256个字节 |**Yes**|
| **DestVideoBitrate** | int | 视频码率，单位kbps。 |**Yes**|
| **DestVideoResolution** | string | 视频分辨率，格式为像素宽度x像素高度，例如1280x720。该字段为空表示保持原始视频大小。 |**Yes**|
| **DestVideoCodec** | string | 视频的编码类型 |**Yes**|
| **DestAudioBitrate** | int | 音频码率，单位kbps。 |**Yes**|
| **DestAudioSample** | int | 音频采样率，单位hz。 |**Yes**|
| **DestAudioChannel** | int | 音频声道数量。 |**Yes**|
| **DestFormat** | string | 目标视频格式，可选值为mp4、flv、mpegts。 |**Yes**|
| **DestSuffix** | string | 目标视频的文件名后缀。 |**Yes**|
| **CallbackUrl** | string | 转码任务结束后，回调客户的url地址。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCodecPattenList
```

### 响应示例
    
```json
{
  " CustomizedPattenList": [],
  "Action": "GetCodecPattenListResponse",
  "DefaultPattenList": [
    {
      "CallbackUrl": "",
      "DestAudioBitrate ": 48,
      "DestAudioChannel ": 2,
      "DestAudioSample ": 44100,
      "DestFormat ": "mp4",
      "DestSuffix": "_480p",
      "DestVideoBitrate ": 500,
      "DestVideoResolution ": "864x480",
      "PattenId": "1",
      "PattenName": "默认480p-mp4"
    }
  ],
  "RetCode": 0
}
```





