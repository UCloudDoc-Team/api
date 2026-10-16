# 列出用户关联的IAM策略 - ListPoliciesForUser

## 简介

列出用户关联的IAM策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListPoliciesForUser)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListPoliciesForUser`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UserName** | string | 用户名 |**Yes**|
| **Scope** | string | 应用范围 |No|
| **ProjectID** | string | 项目ID |No|
| **Limit** | string | 需要查询的用户组数量 |No|
| **Offset** | string | 从第几条数据开始查询 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 权限策略问数 |**Yes**|
| **Policies** | array[[*AttachedPolicy*](#AttachedPolicy)] | 权限策略列表 |**Yes**|

#### 数据模型


#### AttachedPolicy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PolicyName** | string | 权限策略名称 |**Yes**|
| **PolicyURN** | string | 策略URN |**Yes**|
| **Scope** | string | 应用范围（ScopeRequired:项目级, ScopeEmpty:全局级, ScopeUnrestricted:项目级/全局级） |**Yes**|
| **AttachedAt** | int | 策略被绑定时的 Unix 时间戳 |**Yes**|
| **Description** | string | 描述 |No|
| **ProjectName** | string | 项目名称 |No|
| **ProjectID** | string | 项目ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListPoliciesForUser
&UserName=WigejYot
&Scope=wpFVoffI
&ProjectID=hKymMuzZ
&Limit=IdUIFcbA
&Offset=XDGiLmJn
```

### 响应示例
    
```json
{
  "Action": "ListPoliciesForUserResponse",
  "Message": "mXttgmqS",
  "Policies": [
    {
      "AttachedAt": 4,
      "CreatedAt": 2,
      "Description": "PDmbkeZM",
      "PolicyName": "PAsWyXOe",
      "PolicyURN": "SXyEkrfh",
      "ProjectID": "nEQZMTkG",
      "Scope": "yes"
    }
  ],
  "RetCode": 0,
  "TotalCount": 4
}
```





