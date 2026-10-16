# 获取策略详情 - GetIAMPolicy

## 简介

获取策略详情






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetIAMPolicy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetIAMPolicy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PolicyURN** | string | 策略URN |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Policy** | [*IAMPolicy*](#IAMPolicy) | 策略信息 |**Yes**|

#### 数据模型


#### IAMPolicy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PolicyName** | string | 策略名称 |No|
| **PolicyURN** | string | IAM权限策略URN |No|
| **Description** | string | IAM权限策略描述 |No|
| **Document** | string | IAM权限策略文本 |No|
| **ScopeType** | string | IAM权限策略应用范围（ScopeRequired:项目级, ScopeEmpty:全局级, ScopeUnrestricted:项目级/全局级） |No|
| **CreatedAt** | int | IAM权限策略创建时间 |No|
| **UpdatedAt** | int | IAM权限策略更新时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetIAMPolicy
&PolicyURN=iAVnENEZ
```

### 响应示例
    
```json
{
  "Action": "GetIAMPolicyResponse",
  "Message": "MJEfQQTC",
  "Policy": {},
  "RetCode": 0
}
```





