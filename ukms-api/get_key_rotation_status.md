# 获取密钥轮转状态 - GetKeyRotationStatus

## 简介

查询密钥自动轮转状态。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetKeyRotationStatus)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetKeyRotationStatus`                        | **Yes** |
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
| **KeyRotationEnabled** | boolean | 是否开启自动轮转。取值：true、false。 |**Yes**|
| **KeyId** | string | 密钥资源长 ID。 |**Yes**|
| **RotationPeriodInDays** | int | 轮转周期，单位天；未开启时返回 0。 |**Yes**|
| **NextRotationDate** | int | 下次轮转时间，Unix 时间戳。 |No|
| **OnDemandRotationStartDate** | int | 按需轮转开始时间，Unix 时间戳。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetKeyRotationStatus
&Region=cn-zj
&ProjectId=cLdEAlgw
&KeyId=VUDmoZDT
```

### 响应示例
    
```json
{
  "Action": "GetKeyRotationStatusResponse",
  "RetCode": 0
}
```





