# 停止异步任务 - StopTask

## 简介

用于停止异步任务

?> 必须在内网调用，不通过api.ucloud.cn




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=StopTask)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `StopTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **TaskId** | string | 异步任务ID |**Yes**|
| **AccessToken** | string | UGC提交任务Token，通过GetAccessToken获得 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TaskId** | string | 所操作的TaskId |No|




## 示例

### 请求示例
    
```
http(s)://api.ugc.service.ucloud.cn/?Action=StopTask
&Region=cn-bj2
&TaskId=d9cb5d99309dce06e0a7adb850878a4635daf49a82145e0637542f8763bff90e
&AccessToken=H2JKDKOW3HN24CGG1PV3DV779932C
```

### 响应示例
    
```json
{
  "Action": "StopTaskResponse",
  "Message": "pUFDfSiL",
  "RetCode": 0
}
```





