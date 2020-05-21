# 加密 - Encrypt

## 简介

用于加密最多为4KB任意数据，诸如RSA密钥，数据库密钥，或者其他敏感的客户信息。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=Encrypt)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `Encrypt`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **KeyId** | string | 调用 CreateKey 接口返回的CMK全局唯一标识符 |**Yes**|
| **Plaintext** | string | 被加密的明文数据，该字符串必须使用base64编码 |**Yes**|
| **EncryptionContext** | string | 加密时传入的加密上下文, 长度不超过 1024 个字符 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CiphertextBlob** | string | 加密后的密文 |**Yes**|
| **Status** | string | 操作结果 |No|
| **RequestUuid** | string | 此次请求唯一标识符 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=Encrypt
&ProjectId=org-mjwvpk
&KeyId=ukms-oep2f0
&Plaintext=QWxsIHRoaW5ncyBpbiB0aGVpciBiZWluZyBhcmUgZ29vZCBmb3Igc29tZXRoaW5nLgo=
&EncryptionContext=/Users/Documents/workspace
```

### 响应示例
    
```json
{
  "Action": "EncryptResponse",
  "CiphertextBlob": "GlT4DX+Aw2aJrmyPBU0cEusjvy3omP1EvRx+X+EmAHQBEx2rAmze7jCY9aaElqB062o7GsaILoDJOtBU.9cA5QefbfM7HCJDTd3FxQl6xLRMu0sT6dPQPppxsW4bh4m4Zx/aK/bm1KqSdNIw5I+OGPRI2zF6sWfiXOkA9dZNU.75WFYw5ZFIWr6p3kNd5YZA==",
  "RequestUuid": "023a8f36-c527-4dcd-815a-8e7f36b63202",
  "RetCode": 0,
  "Status": "success"
}
```





