# 获取异步任务结果 - GetTaskResult

## 简介

获取异步任务的运行结果，该接口请求地址是api.ugc.service.ucloud.cn。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetTaskResult)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetTaskResult`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **TaskId** | string | 任务ID	 |**Yes**|
| **AccessToken** | string | 授权Token	 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **State** | string | 任务运行状态,Running：运行中;Success：成功;Fail：失败<br /> |**Yes**|




## 示例

### 请求示例
    
```
http(s)://api.ugc.service.ucloud.cn/?Action=GetTaskResult
&Region=cn-bj2
&TaskId=123456
```

### 响应示例
    
```json
{
  "Action": "GetTaskResultResponse",
  "Message": "jtumyFth",
  "RetCode": 0,
  "State": "mcPxKxcD"
}
```





