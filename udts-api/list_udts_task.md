# 获取 Task 列表信息 - ListUDTSTask

## 简介

获取用户创建的 Task 信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUDTSTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | string | 偏移量，默认为 0 |No|
| **Limit** | string | 请求数量，默认为 20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ListDataItem*](#ListDataItem)] | ListDataItem 数组 |**Yes**|

#### 数据模型


#### ListDataItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | 任务 ID |No|
| **Name** | string | 任务名称 |No|
| **Type** | string | 任务类型, full全量, incremental增量，full+incremental全量+增量。 |No|
| **MaxRetryCount** | int | 最大失败重试次数 |No|
| **CurRetryCount** | int | 当前失败重试次数 |No|
| **Status** | string | 任务状态 |No|
| **CreateTime** | int | 创建时间 |No|
| **Progress** | [*Progress*](#Progress) | 全量迁移进度信息，增量迁移时为空  |No|

#### Progress

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TotalCount** | int | 总条目数 |No|
| **CurCount** | int | 已迁移条目数 |No|
| **TotalDuration** | int | 估算总耗时间（单位秒） |No|
| **CurDuration** | int | 已耗时间（单位秒） |No|
| **Percentage** | float | 完成进度 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUDTSTask
&Limit=3
&Offset=0
&ProjectId=org-hiny12
```

### 响应示例
    
```json
{
  "Action": "ListUDTSTaskResponse",
  "Data": [
    {
      "CreateTime": 1559630077,
      "CurRetryCount": 0,
      "MaxRetryCount": 0,
      "Name": "test-1",
      "Progress": {
        "CurCount": 0,
        "CurDuration": 0,
        "Percentage": 0,
        "TotalCount": 0,
        "TotalDuration": 0
      },
      "Status": "Created",
      "TaskId": "udts-zzcsnrkx",
      "Type": "full"
    },
    {
      "CreateTime": 1559285642,
      "CurRetryCount": 0,
      "MaxRetryCount": 0,
      "Name": "test-1",
      "Progress": {
        "CurCount": 0,
        "CurDuration": 0,
        "Percentage": 0,
        "TotalCount": 0,
        "TotalDuration": 0
      },
      "Status": "Created",
      "TaskId": "udts-kjl55fxr",
      "Type": "full"
    }
  ],
  "Message": "",
  "RetCode": 0
}
```





