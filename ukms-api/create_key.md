# 创建密钥 - CreateKey

## 简介

创建密钥。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateKey)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateKey`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子账号必须填写。 |No|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **ResourceId** | string | UKMS 实例资源 ID。 |**Yes**|
| **Description** | string | 密钥描述，最多 8192 字符。 |No|
| **Alias** | string | 可选密钥别名，格式为 alias/name。 |No|
| **KeySpec** | string | 密钥规格，默认 SYMMETRIC_DEFAULT（AES_256）。可选值：SYMMETRIC_DEFAULT(AES_256)、RSA_2048、RSA_3072、RSA_4096、ECC_NIST_P256、ECC_NIST_P384、ECC_NIST_P521、HMAC_256、HMAC_384、HMAC_512。 |No|
| **Origin** | string | 密钥材料来源，默认 UCLOUD_KMS。当前仅支持 UCLOUD_KMS；EXTERNAL 为 BYOK 规划值，当前传入会返回 100660。 |No|
| **DeletionProtection** | string | 是否开启删除保护。可选值：true、false；默认 false。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **KeyId** | string | 密钥 ID。 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateKey
&ProjectId=org-mjwvpk
&Description=description
&Alias=nyScYpru
&ResourceId=SswbYBDh
&Description=tgpAssBD
&KeyType=WFZwxWAu
&Region=FToBNQdx
```

### 响应示例
    
```json
{
  "Action": "CreateKeyResponse",
  "CreatedTime": 1545049380,
  "Description": "description",
  "Enabled": true,
  "KeyId": "ukms-xxxx",
  "LastModifiedTime": 1545049380,
  "RequestUuid": "91a4229e-3c9f-4a81-85ab-68c6a14f3f99",
  "RetCode": 0,
  "Status": "success"
}
```





