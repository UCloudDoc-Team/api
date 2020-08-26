# 获取域名刷新任务状态 - DescribeNewUcdnRefreshCacheTask

## 简介

获取域名刷新任务状态






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNewUcdnRefreshCacheTask)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNewUcdnRefreshCacheTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **TaskId.N** | string | 提交任务时返回的任务ID |No|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值 |No|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。 |No|
| **Status** | string | 需要获取的内容刷新的状态，枚举值：success：成功；wait：等待处理；process：正在处理；failure：失败； unknow：未知，默认选择所有状态 |No|
| **Offset** | int | 数据偏移量，默认为0，自然数 |No|
| **Limit** | int | 返回数据长度,默认全部，自然数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 刷新任务的总数 |No|
| **TaskList** | array[[*TaskInfo*](#TaskInfo)] | 刷新任务信息，参考TaskInfo |No|

#### 数据模型


#### TaskInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | 提交任务时返回的任务ID |No|
| **UrlLists** | array[[*UrlProgressInfo*](#UrlProgressInfo)] | 任务url的信息列表，参考UrlProgressInfo |No|
| **Type** | string | file/dir  刷新任务会返回Type，预取任务没有 |No|
| **CreateTime** | int | 刷新任务创建的时间。格式为Unix Timestamp |No|
| **Status** | string | 刷新任务的当前状态，枚举值：success：成功；wait：排队中；process：处理中；failure：失败； unknow：未知 |No|

#### UrlProgressInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Url** | string | 刷新的单条url |No|
| **CreateTime** | int | 刷新任务创建的时间。格式为Unix Timestamp |No|
| **FinishTime** | int | 任务完成时间。格式为Unix Timestamp |No|
| **Status** | string | 刷新任务的当前状态，枚举值：success：成功；wait：排队中；process：处理中；failure：失败； unknow：未知 |No|
| **Progress** | int | 刷新进度，单位% |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNewUcdnRefreshCacheTask
&ProjectId=xxxxxx
&TaskId.n=sHemHKgw
&BeginTime=2
&EndTime=6
&Status=JNhEgMiG
&Offset=3
&Limit=9
```

### 响应示例
    
```json
{
  "Action": "DescribeNewUcdnRefreshCacheTaskResponse",
  "RetCode": 0,
  "TaskList": [
    {
      "CreateTime": 1548051097,
      "Status": "success",
      "TaskId": "20190121141137_4d8031d5",
      "Type": "file",
      "UrlLists": [
        {
          "CreateTime": 1548051097,
          "FinishTime": 1548051103,
          "Progress": 100,
          "Status": "success",
          "Url": "http://xxxxx/test2.jpg"
        },
        {
          "CreateTime": 1548051097,
          "FinishTime": 1548051103,
          "Progress": 100,
          "Status": "success",
          "Url": "http://xxxxx/test.jpg"
        }
      ]
    }
  ],
  "TotalCount": 2
}
```





