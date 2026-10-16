# 直播录制文件统计信息 - GetULiveRecordFileInfo

## 简介

直播录制文件统计






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveRecordFileInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveRecordFileInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Domain** | string | 域名 |**Yes**|
| **AccessPoint** | string | 接入点名称 |**Yes**|
| **StartTime** | int | 查询起始时间 |**Yes**|
| **EndTime** | int | 查询结束时间，按天粒度，可查最近7天，最多查一个月 |**Yes**|
| **StreamName** | string | 流名称,不填表示获取所有流 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*GetULiveRecordFileInfoData*](#GetULiveRecordFileInfoData)] | RetCode为0，统计信息，参考GetULiveRecordFileInfoData |**Yes**|

#### 数据模型


#### GetULiveRecordFileInfoData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccessPoint** | string | 接入点 |**Yes**|
| **StreamName** | string | 流名称 |**Yes**|
| **StartTime** | string | 录制起始时间，格式：时间戳字符串 |**Yes**|
| **EndTime** | string | 录制截止时间，格式：时间戳字符串 |**Yes**|
| **Duration** | string | 录制时长，单位秒 |**Yes**|
| **Size** | string | 录制文件大小，单位B |**Yes**|
| **Url** | string | 获取录制文件URL |**Yes**|
| **Type** | string | 录制类型 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveRecordFileInfo
&ProjectId=xxXCMnqY
&Domain=OhlFHDIU
&AccessPoint=uYCzQOMT
&StartTime=5
&EndTime=2
&StreamName=ZRKmkDOw
```

### 响应示例
    
```json
{
  "Action": "GetULiveRecordFileInfoResponse",
  "Data": [
    {
      "AccessPoint": "cKJBumEx",
      "Duration": "FvJNzqWV",
      "EndTime": "UzlivKnJ",
      "Size": "QLrLqcVx",
      "StartTime": "HKPtwtSq",
      "StreamName": "JIfPEwJY",
      "Url": "VOXeXxOB"
    }
  ],
  "RetCode": 0
}
```





