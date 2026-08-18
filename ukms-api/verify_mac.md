# 验证Mac签名 - VerifyMac

## 简介

验证签名






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=VerifyMac)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `VerifyMac`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **KeyId** | string | 密钥ID |**Yes**|
| **MacMessage** | string | 用于验证的消息。请输入与生成 HMAC 时所用消息相同的消息。 |**Yes**|
| **Mac** | string | 要验证的 HMAC。请输入由 GenerateMac 操作生成的 HMAC，前提是您指定的消息、HMAC KMS 密钥和 MAC 算法与此请求中指定的值相同。 |**Yes**|
| **MacAlgorithm** | string | 验证过程中将使用的 MAC 算法。请输入与计算 HMAC 时相同的 MAC 算法。<br />此算法必须受 KeyId 参数标识的 HMAC KMS 密钥支持。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **KeyId** | string | 密钥ID |No|
| **MacAlgorithm** | string | 验证中使用的 MAC 算法。 |No|
| **MacValid** | boolean | 一个布尔值，表示 HMAC 是否已验证。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=VerifyMac
&Region=cn-zj
&ProjectId=kkUmmBBT
&Key=xjwXgLPx
&MacMessage=LMlYzCed
&Mac=VZBKySnc
&MacAlgorithm=WqhhThlY
```

### 响应示例
    
```json
{
  "Action": "VerifyMacResponse",
  "RetCode": 0
}
```





