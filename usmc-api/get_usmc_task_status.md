# 查看任务状态 - GetUSMCTaskStatus

## 简介

查看任务状态









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUSMCTaskStatus`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PlanId** | string | 迁移计划ID |**Yes**|
| **TaskId** | string | 任务ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*TaskStatus*](#TaskStatus) | TaskStatus |**Yes**|

#### 数据模型


#### TaskStatus

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Progress** | [*ProgressData*](#ProgressData) | 进度 |No|
| **State** | string | 状态 |No|
| **FailedMessage** | string | 错误信息 |No|

#### ProgressData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Percentage** | float | 进度百分比 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUSMCTaskStatus
&ProjectId=shafqzkV
&TaskId=xWgrvsUz
```

### 响应示例
    
```json
{
  "Action": "GetUSMCTaskStatusResponse",
  "Data": {},
  "Message": "bEoqNfyv",
  "RetCode": 0
}
```





