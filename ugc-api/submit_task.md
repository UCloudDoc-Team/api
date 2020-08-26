# 提交任务 - SubmitTask

## 简介

获取提交的任务列表，备注：该接口的Content-Type 应为application/octet-stream，传入数据以二进制数据流的形式POST发送。请求地址是api.ugc.service.ucloud.cn






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=SubmitTask)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SubmitTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ImageName** | string | 任务使用的镜像名 |**Yes**|
| **AccessToken** | string | 授权Token	 |**Yes**|
| **Cmd** | string | docker镜像运行参数	 |No|
| **OutputDir** | string | 算法输出的文件目录	 |No|
| **OutputFileName** | string | 算法输出的文件名称，支持输出到多个文件，如OutputFileName=output1&OutputFileName=output2 |No|
| **TaskType** | string | 同步任务Sync，异步任务Async，默认Async	 |No|
| **TimeOut** | int | 超时时间同步任务默认值为10秒，异步任务为默认为0，0表示不限制	 |No|
| **TaskName** | string | 任务名称	 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TaskId** | string | 任务ID(只有异步任务会返回该字段)<br /> |**Yes**|




## 示例

### 请求示例
    
```
http(s)://api.ugc.service.ucloud.cn/?Action=SubmitTask
&Region=cn-bj2
&ImageName=ucsdr.ucloud.cn:5000/ucs/helloworld:6
&OutputDir=/tmp
&OutputFileName=output
```

### 响应示例
    
```json
{
  "Action": "SubmitTaskResponse",
  "Message": "wTbCqKAn",
  "RetCode": 0,
  "TaskId": "Wkxflnwp"
}
```





