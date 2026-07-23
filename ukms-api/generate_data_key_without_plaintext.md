# 创建数据密钥（无明文） - GenerateDataKeyWithoutPlaintext

## 简介

创建数据密钥（无明文），仅返回加密后的数据密钥。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GenerateDataKeyWithoutPlaintext)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GenerateDataKeyWithoutPlaintext`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子账号必须填写。 |No|
| **ResourceId** | string | UKMS 实例资源 ID。 |**Yes**|
| **KeyId** | string | 密钥资源长 ID、ARN 或别名。 |**Yes**|
| **KeySpec** | string | 数据密钥规格。可选值：AES_256、AES_128；默认 AES_256。与 NumberOfBytes 二选一，同时填写时 NumberOfBytes 优先。 |No|
| **NumberOfBytes** | int | 生成数据密钥的字节长度，取值范围 1\~1024。与 KeySpec 二选一，同时填写时本字段优先。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CiphertextBlob** | string | 加密后的数据密钥。 |**Yes**|
| **KeyId** | string | 加密该数据密钥的密钥资源长 ID。 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GenerateDataKeyWithoutPlaintext
&Region=cn-zj
&ProjectId=xSPzCikl
&KeyId=MXAvQpBb
```

### 响应示例
    
```json
{
  "Action": "GenerateDataKeyWithoutPlaintextResponse",
  "RetCode": 0
}
```





