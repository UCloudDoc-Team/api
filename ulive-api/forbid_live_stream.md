# 对一个直播流实施禁播 - ForbidLiveStream

## 简介

对一个直播流实施禁播






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ForbidLiveStream)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ForbidLiveStream`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 推流域名 |**Yes**|
| **Application** | string | 禁播流所属的Application(应用名) |**Yes**|
| **StreamId** | string | 禁播流Id |**Yes**|
| **ForbidDuration** | int | 禁播时长（默认30天） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ForbidLiveStream
&PublishDomain=PUFAIMtW
&Application=DupmoAoM
&StreamId=oBkRtfjQ
&ForbidDuration=8
```

### 响应示例
    
```json
{
  "Action": "ForbidLiveStreamResponse",
  "RetCode": 0
}
```





