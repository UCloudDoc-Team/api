# 解密 - Decrypt

## 简介

用于解密密文数据，得到明文数据。（该密文数据必须是通过 GenerateDataKey 或 Encrypt 接口生成的。）





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=Decrypt)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

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
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **CiphertextBlob** | string | 由 GenerateDataKey 或 Encrypt 生成的加密后的数据密钥 |**Yes**|
| **EncryptionContext** | string | 解密时传入的加密上下文，如果调用GenerateDataKey 或者 Encrypt 时传了该值，则与之前保持一致，长度不超过 1024 个字符 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **KeyId** | string | 加密该数据密钥的主密钥的 KeyId |**Yes**|
| **Plaintext** | string | 解密后数据密钥的明文 |**Yes**|
| **Status** | string | 操作结果 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=Decrypt
&ProjectId=org-mjwvpk
&CiphertextBlob=be0sNdakG9SmQu+dJc1mQgMMWPubCI3Wjp8S6/kg6PksBKrcV18j/uPtCRKjDeRhviBRs33yKmudXel6.KiQ4h/5NIk3mYj7//c5DmgUr8juQ2WwajYfZ7GJYU8vjk4N+32Em+dpn2VoOVAvFDjovmLUUn7wpXd4Z13mA35Cm.LxUAY5umOfawSgIKbMZtLQ==
&EncryptionContext=/Users/Documents/workspace
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





