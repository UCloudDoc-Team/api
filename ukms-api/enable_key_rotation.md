# 开启密钥轮转 - EnableKeyRotation

## 简介

开启对称密钥自动轮转。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=EnableKeyRotation)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `EnableKeyRotation`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子账号必须填写。 |No|
| **ResourceId** | string | UKMS 实例资源 ID。 |**Yes**|
| **KeyId** | string | 密钥 ID、ARN 或别名。 |**Yes**|
| **RotationPeriodInDays** | int | 轮转周期，单位天。取值范围 1\~2560，默认 365。仅 SYMMETRIC_DEFAULT 且 Origin=UCLOUD_KMS 的密钥支持轮转。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=EnableKeyRotation
&Region=cn-zj
&ProjectId=iYBlbIRH
&KeyId=arcoFptY
```

### 响应示例
    
```json
{
  "Action": "EnableKeyRotationResponse",
  "RetCode": 0
}
```





