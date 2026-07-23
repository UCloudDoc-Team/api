# 查看主密钥 - DescribeKey

## 简介

查看指定密钥的元数据。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeKey)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeKey`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子账号必须填写。 |No|
| **ResourceId** | string | UKMS 实例资源 ID。 |**Yes**|
| **KeyId** | string | 密钥资源长 ID、ARN 或别名。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **KeyMetadata** | [*KeyMetadata*](#KeyMetadata) | 密钥元数据。 |**Yes**|

#### 数据模型


#### KeyMetadata

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **KeyId** | string | 密钥资源长 ID。 |**Yes**|
| **CreationDate** | int | 创建时间，Unix 时间戳。 |**Yes**|
| **Enabled** | string | 是否启用。取值：true、false。 |**Yes**|
| **Description** | string | 密钥描述。 |No|
| **KeyUsage** | array[string] | 密钥用途。取值：ENCRYPT_DECRYPT、SIGN_VERIFY、GENERATE_VERIFY_MAC、KEY_AGREEMENT。 |**Yes**|
| **KeyState** | string | 密钥对外状态。取值：Enabled、Disabled、PendingDeletion、PendingImport、Unavailable。 |**Yes**|
| **DeletionDate** | int | 计划删除时间，Unix 时间戳。 |No|
| **Origin** | string | 密钥材料来源。取值：UCLOUD_KMS、EXTERNAL；当前 CreateKey 仅支持 UCLOUD_KMS。 |**Yes**|
| **KeySpec** | string | 密钥规格。取值：SYMMETRIC_DEFAULT、RSA_2048、RSA_3072、RSA_4096、ECC_NIST_P256、ECC_NIST_P384、ECC_NIST_P521、HMAC_256、HMAC_384、HMAC_512。 |**Yes**|
| **DeletionProtection** | string | 是否开启删除保护。取值：true、false。 |**Yes**|
| **KeyVersion** | int | 当前密钥版本。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeKey
&ProjectId=org-mjwvpk
&KeyId=ukms-oep2f0
&Region=didlIBnd
&ResouceId=uMFPZuZo
```

### 响应示例
    
```json
{
  "Action": "DescribeKeyResponse",
  "Alias": "vKdnnfCj",
  "CreatedTime": 1,
  "Description": "jXLaGikX",
  "Enabled": true,
  "KeyId": "ukms-xxxx",
  "LastModifiedTime": 7,
  "RequestUuid": "093399-ssxbcbc-3423444",
  "RetCode": 0,
  "Status": "success",
  "Type": "CustomerManagedKeys"
}
```





