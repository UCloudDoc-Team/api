# 列出用户组关联的权限策略 - ListPoliciesForGroup

## 简介

列出用户组关联的权限策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListPoliciesForGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListPoliciesForGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GroupName** | string | 用户组名称 |**Yes**|
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
| **Policies** | array[[*Policy*](#Policy)] | 用户信息数组 |**Yes**|
| **TotalCount** | int | 总数 |**Yes**|

#### 数据模型


#### Policy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PolicyName** | string | 权限策略名称 |**Yes**|
| **PolicyURN** | string | 策略URN |**Yes**|
| **Description** | string | 描述 |No|
| **CreatedAt** | int | 创建时间 |No|
| **Scope** | string | 应用范围（ScopeRequired:项目级, ScopeEmpty:全局级, ScopeUnrestricted:项目级/全局级） |No|
| **ProjectID** | string | 项目ID |No|
| **AttachedAt** | int | 策略被添加到用户组时的时间戳 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListPoliciesForGroup
&GroupName=VHldJkYs
&Scope=tbLpJnNP
&ProjectID=zDsUSYuA
&Limit=mEGbXyIu
&Offset=ZFxUpmzZ
```

### 响应示例
    
```json
{
  "Action": "ListPoliciesForGroupResponse",
  "Message": "ltpagPiP",
  "Policies": [
    {
      "AttachedAt": 3,
      "CreatedAt": 6,
      "Description": "BRMFCakF",
      "PolicyName": "piAGjTUK",
      "PolicyURN": "HLSbhbvw",
      "ProjectID": "JbJFDksq",
      "Scope": "yes"
    }
  ],
  "RetCode": 0,
  "TotalCount": 7
}
```





