# 获取轻量云主机OpenClaw渠道二维码 - GetULHostOpenClawChannelQRCode

## 简介

获取轻量云主机OpenClaw渠道二维码






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULHostOpenClawChannelQRCode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClawChannel** | string | OpenClaw渠道，如qqbot，wechat，wecom，feishu，dingtalk |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **QRCode** | string | 二维码，用于后续轮询 |**Yes**|
| **QRCodeURL** | string | 二维码地址 |**Yes**|
| **QRCodePNG** | string | 二维码图片，以base64编码 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULHostOpenClawChannelQRCode
&ClawChannel=eYVcYEMe
```

### 响应示例
    
```json
{
  "Action": "GetULHostOpenClawChannelQRCodeResponse",
  "QRCode": "XeVcPJto",
  "QRCodePNG": "tnzKbhGk",
  "QRCodeUrl": "JSTHzuTI",
  "RetCode": 0
}
```





