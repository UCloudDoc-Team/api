# 移除硬件隔离组中的主机 - LeaveIsolationGroup

## 简介

移除硬件隔离组中的主机






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=LeaveIsolationGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `LeaveIsolationGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区信息 |No|
| **ProjectId** | string | 项目id |No|
| **GroupId** | string | 硬件隔离组id |**Yes**|
| **UHostId** | string | 主机id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UHostId** | string | 主机id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=LeaveIsolationGroup
&Region=cn-zj
&GroupId=sqDxnHTy
&UHostId=cqCgEwrJ
&Zone=iuFbLPDX
&ProjectId=BoXqQbGF
```

### 响应示例
    
```json
{
  "Action": "LeaveIsolationGroupResponse",
  "GroupId": "ZyzDZUeZ",
  "RetCode": 0
}
```





