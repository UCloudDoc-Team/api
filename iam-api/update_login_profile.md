# 更新用户登录资料 - UpdateLoginProfile

## 简介

更新用户登录资料






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateLoginProfile)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateLoginProfile`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UserName** | string | 用户名 |**Yes**|
| **Status** | string | 登录资料状态 |No|
| **UserEmail** | string | 用户真实邮箱 |No|
| **Password** | string | 设置子账号密码 |No|
| **MaxPasswordAge** | int | 设置子账号密码有效时间 |No|
| **MFABindRequired** | boolean | 设置子账号登录必须绑定MFA验证 |No|
| **PasswordResetRequired** | boolean | 设置子账号下次登录必须重置密码 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateLoginProfile
&UserName=Alice
&MFABindRequired=true
&MaxPasswordAge=90
&Status=Active
&UserEmail=alice@ucloud.cn
&MFABindRequired=false
&MaxPasswordAge=4
&Password=qgAcTpbT
&PasswordResetRequired=false
```

### 响应示例
    
```json
{
  "Message": "Success",
  "RetCode": 0
}
```





