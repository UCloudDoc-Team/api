# 创建IAM用户 - CreateUser

## 简介

创建IAM用户






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUser)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUser`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UserName** | string | 用户名 |**Yes**|
| **AccessKeyStatus** | string | API密钥访问状态（LoginProfileStatus值为Inactive时，AccessKeyStatus不能为Inactive） |**Yes**|
| **LoginProfileStatus** | string | 控制台登录访问状态（AccessKeyStatus值为Inactive时，LoginProfileStatus不能为Inactive） |**Yes**|
| **Email** | string | 用户邮箱（LoginProfileStatus值等于Active必传，LoginProfileStatus值等于Inactive不传） |No|
| **DisplayName** | string | 显示名称 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UserEmail** | string | 用户邮箱 |No|
| **AccessKeyID** | string | 密钥ID |No|
| **AccessKeySecret** | string | 密钥凭证 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUser
&Email=XKiuwnTS
&UserName=XbNfvNDN
&DisplayName=JXunzBGt
&MobilePhone=EBrJVWSk
&AccessKeyStatus=Inactivate
&LoginProfileStatus=Inactivate
```

### 响应示例
    
```json
{
  "AccessKeyID": "ACOgeKDN",
  "AccessKeySecret": "mNEyDWfT",
  "Action": "CreateUserResponse",
  "Message": "yyKMMKyR",
  "RetCode": 0,
  "UserEmail": "ewLZVcgB"
}
```





