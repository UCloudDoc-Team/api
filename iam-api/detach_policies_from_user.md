# 移除用户关联的IAM策略 - DetachPoliciesFromUser

## 简介

移除用户关联的IAM策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DetachPoliciesFromUser)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DetachPoliciesFromUser`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UserName** | string | 用户名 |**Yes**|
| **PolicyURNs.N** | string | 策略URN |**Yes**|
| **Scope** | string | 应用范围 |**Yes**|
| **ProjectID** | string | 项目ID（当Scope=Specified时ProjectID必传） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DetachPoliciesFromUser
&UserName=hHBCEztQ
&PolicyURNs.N=cIPBLhur
&Scope=All
&ProjectID=joEaCHdV
```

### 响应示例
    
```json
{
  "Action": "DetachPoliciesFromUserResponse",
  "Message": "mzRxfedh",
  "RetCode": 0
}
```





