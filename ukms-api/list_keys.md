# 获取主密钥列表 - ListKeys

## 简介

查询用户的主密钥信息列表。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListKeys)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListKeys`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子账号必须填写。 |No|
| **ResourceId** | string | UKMS 实例资源 ID。 |**Yes**|
| **Alias** | string | 按密钥 ID 或别名模糊过滤。 |No|
| **Offset** | int | 列表起始位置偏移量。 |No|
| **Limit** | int | 返回数据长度。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*DEK*](#DEK)] | 密钥信息数组，每项为 DEK/ListKeys item。 |**Yes**|
| **TotalCount** | int | 符合条件的总数，不同于 Limit。 |**Yes**|

#### 数据模型


#### DEK

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **KeyId** | string | 对外主密钥 ID（ukms_key_info.key_id）。 |**Yes**|
| **KeySpec** | string | 密钥规格。取值：SYMMETRIC_DEFAULT、RSA_2048、RSA_3072、RSA_4096、ECC_NIST_P256、ECC_NIST_P384、ECC_NIST_P521、HMAC_256、HMAC_384、HMAC_512。 |**Yes**|
| **KeyUsage** | array[string] | 按 KeySpec 派生的密钥用途。取值：ENCRYPT_DECRYPT、SIGN_VERIFY、GENERATE_VERIFY_MAC、KEY_AGREEMENT。 |**Yes**|
| **Origin** | string | 密钥来源，由 Origin 派生。取值：ucloud、import。当前 CreateKey 仅支持 ucloud。 |**Yes**|
| **Status** | string | 数据库密钥状态。常见取值：Active、Deactivated。 |**Yes**|
| **CreatedTime** | int | 创建时间，Unix 时间戳。 |**Yes**|
| **UpdateTime** | int | 更新时间，Unix 时间戳。 |**Yes**|
| **KeyRotationEnabled** | boolean | 是否已开启自动轮转；未配置或已关闭均为 false |**Yes**|
| **RotationPeriodInDays** | int | 自动轮转周期(天)；未开启时为 0 |**Yes**|
| **Description** | string | 密钥描述。 |No|
| **PlanDeleteTime** | int | 计划删除时间，Unix 时间戳。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListKeys
&ProjectId=org-mjwvpk
&OrderBy=-created_time
&Limit=10
&Offset=1
```

### 响应示例
    
```json
{
  "Action": "ListKeysResponse",
  "Objects": [
    {
      "CreatedTime": 1545046660,
      "Description": "test description",
      "Enabled": true,
      "KeyId": "e675e01060b748488d9c58eb5a8e0701",
      "LastModifiedTime": 1545046660
    },
    {
      "CreatedTime": 1544781647,
      "Description": "test description",
      "Enabled": true,
      "KeyId": "1765de4951b9470bab6758c3838806fa",
      "LastModifiedTime": 1544781647
    }
  ],
  "RequestUuid": "7180ba66-bc0a-45af-9789-37e6ed04763b",
  "RetCode": 0,
  "Status": "success",
  "TotalCount": 1
}
```





