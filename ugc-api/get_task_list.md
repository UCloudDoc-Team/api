# 查询任务列表 - GetTaskList

## 简介

获取提交的任务列表。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetTaskList)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetTaskList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **StartTime** | int | 时间检索起始时间 |**Yes**|
| **EndTime** | int | 时间检索结束时间 |**Yes**|
| **TaskId** | string | 任务ID，不填返回所有Id的任务 |No|
| **TaskName** | string | 任务名称，不填返回所有名称的任务 |No|
| **ImageName** | string | 任务运行对应的镜像名 |No|
| **TaskType** | string | 同步任务Sync，异步任务Async；默认为All |No|
| **State** | string | All:所有任务，Running：运行中，Success：成功，Fail：失败；默认为ALL |No|
| **OrderBy** | string | Default: 默认排序 |No|
| **Limit** | int | 返回数据长度，默认为20 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的任务总数 |No|
| **TaskSet** | array[[*UgcTaskSet*](#UgcTaskSet)] | JSON格式的任务列表 参数见 UgcTaskSet |No|

#### 数据模型


#### UgcTaskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | 任务ID |No|
| **TaskName** | string | 任务名称 |No|
| **TaskType** | string | 同步任务Sync，异步任务Async |No|
| **Owner** | string | 任务创建者 |No|
| **State** | string | Running：运行中，Success：成功，Fail：失败 |No|
| **CreateTime** | int | 创建时间，格式为Unix时间戳 |No|
| **StartTime** | int | 开始时间，格式为Unix时间戳 |No|
| **EndTime** | int | 结束时间，格式为Unix时间戳 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetTaskList
&Region=cn-bj2
```

### 响应示例
    
```json
{
  "Action": "GetTaskListResponse",
  "Message": "",
  "RetCode": 0,
  "TaskSet": [
    {
      "CreateTime": 1234567890,
      "EndTime": 1234567990,
      "Owner": "ucs",
      "StartTime": 1234567892,
      "State": "Success",
      "TaskId": "0b560b1d-f3b1-43de-a492-08875d79211b",
      "TaskName": "ucs-helloworld"
    }
  ],
  "TotalCount": 1
}
```





