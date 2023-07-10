# 获取扮演角色的临时身份凭证 - AssumeRole

## 简介

获取扮演角色的临时身份凭证






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AssumeRole)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AssumeRole`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RoleUrn** | string | 要扮演的RAM角色URN。 |**Yes**|
| **RoleSessionName** | string | 角色会话名称。 |**Yes**|
| **DurationSeconds** | int | Token有效期。 |No|
| **Policy** | string | 为STS Token额外添加的一个权限策略，进一步限制STS Token的权限。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Credentials** | [*Credentials*](#Credentials) | 访问凭证。 |No|

#### 数据模型


#### Credentials

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SecurityToken** | string | 安全令牌。 |**Yes**|
| **AccessKeyId** | string | 密钥ID。 |**Yes**|
| **AccessKeySecret** | string | 密钥Secret。 |**Yes**|
| **Expiration** | string | Token到期失效时间（UTC时间）。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AssumeRole
&RoleURN=hHWsZdmn
&RoleSessionName=qtwOJxUr
&DurationSeconds=5
&Policy=LaNpzwGr
```

### 响应示例
    
```json
{
  "Action": "AssumeRoleResponse",
  "Credentials": {},
  "RetCode": 0
}
```





