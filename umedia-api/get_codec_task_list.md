# 获取转码任务列表 - GetCodecTaskList

## 简介

获取转码任务列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCodecTaskList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCodecTaskList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | int | 查询的开始时间，单位：unix时间戳。如果不传，若没有传结束时间，则为当前时间的前七天。否则为结束时间的前七天。 |No|
| **EndTime** | int | 查询的结束时间，单位：unix时间戳。如果不传，若没有传开始时间，则为当前时间，否则为开始时间的后七天。EndTime必须为当前时间往前一个月内，也就是支持一个月内的任务查询。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TaskList** | array[[*CodecPattenInfo*](#CodecPattenInfo)] | 任务信息列表 |No|

#### 数据模型


#### CodecPattenInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | 任务ID |**Yes**|
| **SrcUrl** | string | 原始视频url地址 |**Yes**|
| **DestVideoName** | string | 输出文件名 |**Yes**|
| **DestBucket** | string | 输出文件的存储空间 |**Yes**|
| **DestFormat** | string | 输出视频封装格式 |**Yes**|
| **Duration** | int | 视频时长，单位：秒。只有当任务状态为处理完成时，该参数有意义，其他状态该参数为0。 |**Yes**|
| **CodecLevel** | string | 转码清晰度：superdefinition、highdefinition、mediumdefinition、lowdefinition，分别对应计费的4种规格。只有当任务状态为处理完成时，该参数有意义，其他状态该参数为空字符串。 |**Yes**|
| **CreateTime** | int | 任务创建时间，单位：Unix时间戳 |**Yes**|
| **Status** | string | 任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCodecTaskList
```

### 响应示例
    
```json
{
  "Action": "GetCodecTaskListResponse",
  "RetCode": 0,
  "TaskList": [
    {
      "CodecLevel": "superdefinition",
      "CreateTime ": 1496359861,
      "DestBucket": "video.cn-bj.ufileos.com",
      "DestFormat": "mp4",
      "DestVideoName": "myvideo_hd.mp4",
      "Duration": 155,
      "SrcUrl": "http://video.ucloud.cn/myvideo.mp4",
      "Status": "finished",
      "TaskId": "1"
    }
  ]
}
```





