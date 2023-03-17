# 列出用户组包含的用户 - ListUsersForGroup

## 简介

列出用户组包含的用户






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUsersForGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUsersForGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GroupName** | string | 用户组名称 |**Yes**|
| **Limit** | string | 需要查询的组内用户数量 |No|
| **Offset** | string | 从第几条数据开始查询 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Users** | array[[*UserForGroup*](#UserForGroup)] | 用户信息数组 |**Yes**|
| **TotalCount** | int | 总数 |**Yes**|

#### 数据模型


#### UserForGroup

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Email** | string | 邮箱 |**Yes**|
| **UserName** | string | 用户名 |**Yes**|
| **DisplayName** | string | 昵称 |No|
| **JoinedAt** | int | 用户被添加到用户组时的时间戳 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUsersForGroup
&GroupName=KuKDjeCr
&Limit=JQyYOWCO
&Offset=PrpveeyA
```

### 响应示例
    
```json
{
  "Action": "ListUsersForGroupResponse",
  "Message": "XECMcnes",
  "RetCode": 0,
  "TotalCount": 8,
  "Users": [
    {
      "CreateAt": 6,
      "DisplayName": "nEiDkUhx",
      "Email": "yDPYuLBl",
      "JoinedAt": "EWhIPVXP",
      "Status": "yes",
      "UserName": "NWwNBOgF"
    }
  ]
}
```





