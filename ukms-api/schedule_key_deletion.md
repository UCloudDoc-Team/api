# 计划删除密钥 - ScheduleKeyDeletion

## 简介

计划删除指定密钥。

?> UCloud管理密钥 不能删除。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ScheduleKeyDeletion)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ScheduleKeyDeletion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子账号必须填写。 |No|
| **ResourceId** | string | UKMS 实例资源 ID。 |**Yes**|
| **KeyId** | int | 密钥 DB 数字 ID。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ScheduleKeyDeletion
&ProjectId=org-mjwvpk
&KeyId=ukms-xkxxse
&ResourceId=nHiSzBYZ
&ResourceId=qkGYaDQP
```

### 响应示例
    
```json
{
  "Action": "ScheduleKeyDeletionResponse",
  "RequestUuid": "18726098-1996-4d68-9661-052e3662bae3",
  "RetCode": 0,
  "Status": "success"
}
```





