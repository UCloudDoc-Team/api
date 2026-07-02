# 列出角色关联的权限策略 - ListPoliciesForRole

## 简介

列出角色关联的权限策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListPoliciesForRole)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListPoliciesForRole`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RoleName** | string | 角色名称 |**Yes**|
| **Scope** | string | 范围 |No|
| **ProjectID** | string | 项目标识 |No|
| **Limit** | string | 返回数据长度，默认为10，最大100 |No|
| **Offset** | string | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 权限策略总数 |No|
| **Policies** | array[[*AttachedPolicy*](#AttachedPolicy)] | 权限策略列表 |No|

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
https://api.ucloud.cn/?Action=ListPoliciesForRole
&RoleName=vfMDKOvP
&Scope=YKYdzdOw
&ProjectID=ZaDLZrri
&Limit=SdMriPoz
&Offset=dkSAIWox
```

### 响应示例
    
```json
{
  "Action": "ListPoliciesForRoleResponse",
  "Policies": [
    {
      "AttachedAt": 3,
      "Description": "WuKmNORY",
      "PolicyName": "cvLeAbUx",
      "PolicyURN": "uzroiZrD",
      "ProjectID": "NfQcjUCw",
      "ProjectName": "mItNvtEy",
      "Scope": "All"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





