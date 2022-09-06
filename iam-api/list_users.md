# 列出用户列表 - ListUsers

## 简介

列出用户列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUsers)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUsers`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Limit** | string | 分页Limit(默认：10，最大100) |No|
| **Offset** | string | 分页offset |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Users** | array[[*Users*](#Users)] | 用户信息 |**Yes**|
| **TotalCount** | int | 用户数量 |No|

#### 数据模型


#### Users

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Email** | string | 邮箱 |**Yes**|
| **UserName** | string | 用户名 |**Yes**|
| **DisplayName** | string | 昵称 |No|
| **Status** | string | 状态(Active:正常，Inactive:未激活，Frozen:冻结，ConsoleInactive:控制台未激活) |No|
| **CreatedAt** | int | 创建时间戳 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUsers
&Limit=MQsgTdfa
&Offset=WicWKMBK
&Limit=YTQvTMtp
&Offset=xAbIncHa
```

### 响应示例
    
```json
{
  "Action": "ListUsersResponse",
  "Message": "PoepGvmk",
  "RetCode": 0,
  "TotalCount": 1,
  "Users": [
    {
      "CreateAt": 3,
      "DisplayName": "WZQCLnPj",
      "Email": "QlrwqAoa",
      "JoinedAt": "ObCrmEvV",
      "Status": "Activate",
      "UserName": "TFYdQsyN"
    }
  ]
}
```





