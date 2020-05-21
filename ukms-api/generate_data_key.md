# 创建数据密钥 - GenerateDataKey

## 简介

通过指定主密钥换取自动生成的数据密钥






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GenerateDataKey)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GenerateDataKey`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **KeyId** | string | 用于生成数据密钥的主密钥的 KeyId |**Yes**|
| **EncryptionContext** | string | 生成数据密钥时传入的加密上下文, 长度不超过 1024 个字符 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CiphertextBlob** | string | 数据密钥的密文 |**Yes**|
| **Plaintext** | string | 数据密钥的明文, 用于加密数据 |**Yes**|
| **Status** | string | 操作结果 |No|
| **RequestUuid** | string | 此次请求的唯一标识 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GenerateDataKey
&ProjectId=org-mjwvpk
&KeyId=ukms-oep2f0
&EncryptionContext=/Users/Documents/workspace
```

### 响应示例
    
```json
{
  "Action": "GenerateDataKeyResponse",
  "CiphertextBlob": "GlT4DX+Aw2aJrmyPBU0cEusjvy3omP1EvRx+X+EmAHQBEx2rAmze7jCY9aaElqB062o7GsaILoDJOtBU.lO9rRlxNIxodlT6hepKxfZtCdL/QihwrnUk7LyXxgoA=.75WFYw5ZFIWr6p3kNd5YZA==",
  "Plaintext": "IEM+J8/+Nrq97o4bY8O0Vw==",
  "RequestUuid": "ed552313-02e7-40f7-a0bb-a42f39ac053a",
  "RetCode": 0,
  "Status": "success"
}
```





