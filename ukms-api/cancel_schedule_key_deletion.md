# 取消计划删除密钥 - CancelScheduleKeyDeletion

## 简介

取消计划删除密钥






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CancelScheduleKeyDeletion)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CancelScheduleKeyDeletion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **KeyId** | string | 需要查看的主密钥对应的 KeyId |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Status** | string |  操作结果 |**Yes**|
| **RequestUuid** | string | 此次请求唯一标识符 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CancelScheduleKeyDeletion
&ProjectId=CNGdnvTQ
&KeyId=nfxhOYNv
```

### 响应示例
    
```json
{
  "Action": "CancelScheduleKeyDeletionResponse",
  "RequestUuid": "xxxx--yyyy-z90033",
  "RetCode": 0,
  "Status": "success"
}
```





