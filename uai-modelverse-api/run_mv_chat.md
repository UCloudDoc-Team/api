# 聊天 - RunMVChat

## 简介

聊天接口






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RunMVChat`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Role.N** | string | 按时间从老到新传输对话列表集合，需要与Content一一对应<br />Role为本条信息作者的角色，枚举值为user 或 assistant<br />- user 指用户角色输入的信息<br />- assistant 指模型返回的信息 |**Yes**|
| **Content.N** | string | 按时间从老到新传输对话列表集合，需要与Role一一对应<br />Content为本条信息的具体内容 |**Yes**|
| **AppID** | string | 应用 ID |**Yes**|
| **SessionID** | int | 会话 ID (不填写默认创建新会话) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | 状态码描述 |**Yes**|
| **ID** | int | 消息唯一标识 |**Yes**|
| **SessionID** | int | 会话id |**Yes**|
| **Response** | string | 回复内容 |**Yes**|
| **Time** | int | 时间 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RunMVChat
&Prompt=DTAUtpZW
&AppID=gjvyCaRg
&SessionID=3
&Content=uOsqGAyA
```

### 响应示例
    
```json
{
  "Action": "RunMVChatResponse",
  "ID": 6,
  "Msg": "EWskKMcN",
  "Response": "EFZUczjm",
  "RetCode": 0,
  "SessionID": 6,
  "Time": 3
}
```





