# 获取截图任务列表 - GetSnapTaskList

## 简介

获取截图任务列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetSnapTaskList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSnapTaskList`                        | **Yes** |
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
| **TaskList** | array[[*SnapTaskInfo*](#SnapTaskInfo)] | 任务列表 |No|

#### 数据模型


#### SnapTaskInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | 任务ID |**Yes**|
| **SrcUrl** | string | 原始视频url地址 |**Yes**|
| **SnapType** | string | 截图模式，single表示确定时间点单张截图，periodic表示周期截图,dynamic表示为gif截图 |**Yes**|
| **ImageName** | string | 截图输出的文件名。对于周期截图，该字段表示不加后缀的文件名。 |**Yes**|
| **ImageFormat** | string | 图片格式类型 |**Yes**|
| **ImageCount** | int | 截图张数 |**Yes**|
| **CreateTime** | int | 任务创建时间，单位：Unix时间戳 |No|
| **Status** | string | 任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSnapTaskList
```

### 响应示例
    
```json
{
  "Action": "GetSnapTaskListResponse",
  "RetCode": 0,
  "TaskList": [
    {
      "CreateTime": 1496298697,
      "ImageCount": 5,
      "ImageFormat ": "jpg",
      "ImageName": "myvideo.jpg",
      "SnapType": "periodic",
      "SrcUrl": "http://video.ucloud.cn/myvideo.mp4",
      "Status": "finished",
      "TaskId": "1"
    }
  ]
}
```





