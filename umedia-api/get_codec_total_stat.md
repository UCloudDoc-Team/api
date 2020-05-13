# 获取转码使用量统计 - GetCodecTotalStat

## 简介

获取转码使用量统计





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCodecTotalStat)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCodecTotalStat`                        | **Yes** |
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
| **StatSet** | array[[*CodecStatInfo*](#CodecStatInfo)] | 转码使用量数据表 |No|

#### 数据模型


#### CodecStatInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 统计时间，单位：Unix时间戳 |**Yes**|
| **SuperDefinitionTime** | int | 超高清转码时长，单位：秒 |**Yes**|
| **HighDefinitionTime** | int | 超清转码时长，单位：秒 |**Yes**|
| **MidiumDefinitionTime** | int | 高清转码时长，单位：秒 |**Yes**|
| **LowDefinitionTime** | int | 普清转码时长，单位：秒 |**Yes**|
| **TotalTime** | int | 所有清晰度转码时长总和，单位：秒 |**Yes**|
| **VideoCodec** | string | 视频的编码类型 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCodecTotalStat
&begintime=1500220800
&endtime= 1500480000
```

### 响应示例
    
```json
{
  "Action": "GetCodecTotalStatResponse",
  "RetCode": 0,
  "StatSet": [
    {
      "HighDefinitionTime": 0,
      "LowDefinitionTime": 0,
      "MidiumDefinitionTime": 0,
      "SuperDefinitionTime": 0,
      "Time": 1500220800,
      "TotalTime": 0,
      "VideoCodec": "h264"
    },
    {
      "HighDefinitionTime": 0,
      "LowDefinitionTime": 0,
      "MidiumDefinitionTime": 0,
      "SuperDefinitionTime": 0,
      "Time": 1500307200,
      "TotalTime": 0,
      "VideoCodec": "h264"
    },
    {
      "HighDefinitionTime": 0,
      "LowDefinitionTime": 137,
      "MidiumDefinitionTime": 0,
      "SuperDefinitionTime": 0,
      "Time": 1500393600,
      "TotalTime": 137,
      "VideoCodec": "h264"
    },
    {
      "HighDefinitionTime": 137,
      "LowDefinitionTime": 0,
      "MidiumDefinitionTime": 0,
      "SuperDefinitionTime": 0,
      "Time": 1500480000,
      "TotalTime": 137,
      "VideoCodec": "h264"
    }
  ]
}
```





