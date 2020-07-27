# 查看任务详情 - GetTaskDetail

## 简介

查看任务详情。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetTaskDetail)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetTaskDetail`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **TaskId** | string | 任务ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageName** | string | 任务使用的镜像名 |No|
| **Cmd** | string | 镜像运行参数 |No|
| **OutputDir** | string | 输出文件目录 |No|
| **OutputFileName** | string | 输出文件名称 |No|
| **TaskId** | string | 任务ID |No|
| **TaskName** | string | 任务名称 |No|
| **TaskType** | string | 同步任务Sync，异步任务Async |No|
| **Owner** | string | 任务创建者 |No|
| **State** | string | Running：运行中，Success：成功，Fail：失败 |No|
| **CreateTime** | int | 创建时间，格式为Unix时间戳 |No|
| **StartTime** | int | 开始时间，格式为Unix时间戳 |No|
| **EndTime** | int | 结束时间，格式为Unix时间戳 |No|
| **Timeout** | int | 超时时间 |No|
| **StdoutBrief** | string | 任务标准输出概要 |No|
| **StderrBrief** | string | 任务标准错误概要 |No|
| **CPUUsage** | int | CPU使用情况 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetTaskDetail
&Region=cn-bj2
&TaskId=123456
```

### 响应示例
    
```json
{
  "Action": "GetTaskDetailResponse",
  "CPUUsage": 10,
  "Cmd": "",
  "CreateTime": 1234567892,
  "EndTime": 1234567892,
  "ImageName": "ucsdr.ucloud.cn:5000/ucs/helloworld:6",
  "Message": "",
  "OutputDir": "tmp",
  "OutputFileName": "result",
  "Owner": "ucs",
  "RetCode": 0,
  "StartTime": 1234567892,
  "State": "Success",
  "StderrBrief": "",
  "StdoutBrief": "hello world",
  "TaskId": "12345",
  "TaskName": "Hello World Test",
  "TaskType": "Sync",
  "Timeout": 10
}
```





