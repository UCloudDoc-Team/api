# 获取授权Token - GetAccessToken

## 简介

提交任务接口使用AccessToken做身份验证，此接口用于获取AccessToken。



!> 关于AccessToken的说明： AccessToken的有效期为ExpireIn来传达，默认为7200秒，为了保证调用安全，建议不要设置过长的有效期。 用户需要根据有效时间提前去刷新AccessToken。刷新后及旧Token过期前新老AccessToken都可用，保证业务的平滑过渡。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAccessToken)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAccessToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ExpireIn** | int | Token有效时间，默认为7200秒 |No|
| **GrantType** | string | 默认为Task |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AccessToken** | string | 授权Token |No|
| **ExpireIn** | int | Token有效时间 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAccessToken
&Region=cn-bj2
```

### 响应示例
    
```json
{
  "AccessToken": "H2JKDKOW3HN24CGG1PV3DV779932C",
  "Action": "GetAccessTokenResponse",
  "ExpireIn": 7200,
  "Message": "",
  "RetCode": 0
}
```





