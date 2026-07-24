# 解密 - Decrypt

## 简介

您可以使用此操作解密使用对称加密 KMS 密钥或非对称加密 KMS 密钥加密的密文。当 KMS 密钥为非对称密钥时，您必须指定用于加密密文的 KMS 密钥和加密算法。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=Decrypt)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `Decrypt`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子账号必须填写。 |No|
| **CiphertextBlob** | string | 待解密密文。 |**Yes**|
| **ResourceId** | string | UKMS 实例资源 ID。 |No|
| **KeyId** | string | 主密钥 KeyId；对称密钥可空，从 CiphertextBlob 自动识别；非对称必填。 |No|
| **EncryptionAlgorithm** | string | 解密算法。可选值：SYMMETRIC_DEFAULT、RSAES_OAEP_SHA_1、RSAES_OAEP_SHA_256；非对称密钥解密时必填或使用默认 RSAES_OAEP_SHA_256。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Plaintext** | string | 解密后的明文，Base64 编码。 |**Yes**|
| **KeyId** | string | 密钥资源长 ID。 |**Yes**|
| **EncryptionAlgorithm** | string | 实际使用的解密算法。取值：SYMMETRIC_DEFAULT、RSAES_OAEP_SHA_1、RSAES_OAEP_SHA_256。 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=Decrypt
&ProjectId=org-mjwvpk
&CiphertextBlob=be0sNdakG9SmQu+dJc1mQgMMWPubCI3Wjp8S6/kg6PksBKrcV18j/uPtCRKjDeRhviBRs33yKmudXel6.KiQ4h/5NIk3mYj7//c5DmgUr8juQ2WwajYfZ7GJYU8vjk4N+32Em+dpn2VoOVAvFDjovmLUUn7wpXd4Z13mA35Cm.LxUAY5umOfawSgIKbMZtLQ==
&EncryptionContext=/Users/Documents/workspace
&Region=FKybkPcA
&KeyId=WPLMXGjt
```

### 响应示例
    
```json
{
  "Action": "DecryptResponse",
  "KeyId": "ukms-xkxxse",
  "Plaintext": "QWxsIHRoaW5ncyBpbiB0aGVpciBiZWluZyBhcmUgZ29vZCBmb3Igc29tZXRoaW5nLgo=",
  "RequestUuid": "ad74c84f-f696-47a8-a47b-bcdb77033b08",
  "RetCode": 0,
  "Status": "success"
}
```





