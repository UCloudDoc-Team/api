# 获取告警记录列表 - GetAlarmRecordList

## 简介

获取告警记录列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAlarmRecordList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAlarmRecordList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 开始时间，时间戳 |No|
| **EndTime** | int | 结束时间，时间戳（当前仅支持获取时间间隔在31天内的告警记录） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*AlarmRecord*](#AlarmRecord)] | 告警记录列表 |**Yes**|

#### 数据模型


#### AlarmRecord

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域编号 |No|
| **Zone** | string | 可用区编号 |No|
| **ResourceId** | string | 资源id |**Yes**|
| **ResourceType** | string | 资源类型 |**Yes**|
| **Name** | string | 资源名称 |**Yes**|
| **MetricName** | string | 指标名称 |**Yes**|
| **OccurrenceTime** | int | 告警发生时间 |**Yes**|
| **Recovered** | string | 是否恢复 |**Yes**|
| **Threshold** | float | 阈值 |**Yes**|
| **Value** | float | 告警值 |**Yes**|
| **RecoveryTime** | int | 告警恢复时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAlarmRecordList
&ProjectId=ResDQFGv
&BeginTime=923344
&EndTime=5333333
```

### 响应示例
    
```json
{
  "Action": "GetAlarmRecordListResponse",
  "DataSet": [
    {
      "MetricName": "TaRgQmTH",
      "Name": "BXNzRSnO",
      "OccurrenceTime": 8,
      "Recovered": "Yes",
      "RecoveryTime": 8,
      "ResourceId": "fmLxFLkZ",
      "ResourceType": "KAInbahB",
      "Threshold": 7.97572,
      "Value": 9.51639
    },
    {
      "MetricName": "ASPlEaZc",
      "Name": "osdailmY",
      "OccurrenceTime": 5,
      "Recovered": "Yes",
      "RecoveryTime": 9,
      "ResourceId": "bisLTIWp",
      "ResourceType": "WrmwejhS",
      "Threshold": 6.53413,
      "Value": 5.54988
    },
    {
      "MetricName": "KgGCfbqp",
      "Name": "VAFbFRxD",
      "OccurrenceTime": 2,
      "Recovered": "Yes",
      "RecoveryTime": 8,
      "ResourceId": "wCfkteuo",
      "ResourceType": "UTROAYRI",
      "Threshold": 8.72818,
      "Value": 2.27913
    },
    {
      "MetricName": "mWQZYFzM",
      "Name": "XaHhdZLW",
      "OccurrenceTime": 1,
      "Recovered": "Yes",
      "RecoveryTime": 3,
      "ResourceId": "QVQMVclb",
      "ResourceType": "mdedMlZD",
      "Threshold": 9.22554,
      "Value": 2.43968
    },
    {
      "MetricName": "uqQHIXVE",
      "Name": "PvSNXQpZ",
      "OccurrenceTime": 1,
      "Recovered": "Yes",
      "RecoveryTime": 3,
      "ResourceId": "JeHDBIwa",
      "ResourceType": "JgCsxfqS",
      "Threshold": 7.17721,
      "Value": 4.74256
    },
    {
      "MetricName": "uSWEzuJi",
      "Name": "CMzuWovm",
      "OccurrenceTime": 8,
      "Recovered": "Yes",
      "RecoveryTime": 1,
      "ResourceId": "eUISGdGS",
      "ResourceType": "WJOMSayg",
      "Threshold": 6.57864,
      "Value": 1.73251
    },
    {
      "MetricName": "zSIYVqgD",
      "Name": "oEeBdwco",
      "OccurrenceTime": 6,
      "Recovered": "Yes",
      "RecoveryTime": 5,
      "ResourceId": "WdXpvtrI",
      "ResourceType": "gEYdhrGf",
      "Threshold": 1.52272,
      "Value": 9.83791
    },
    {
      "MetricName": "QVYNTUed",
      "Name": "XvyLDfzY",
      "OccurrenceTime": 8,
      "Recovered": "Yes",
      "RecoveryTime": 2,
      "ResourceId": "dZfxKNkY",
      "ResourceType": "JXrsqQwP",
      "Threshold": 4.31349,
      "Value": 3.97248
    },
    {
      "MetricName": "sndStIsR",
      "Name": "ZaEOZbgh",
      "OccurrenceTime": 6,
      "Recovered": "Yes",
      "RecoveryTime": 8,
      "ResourceId": "ojuzjqkF",
      "ResourceType": "LEfmyHmQ",
      "Threshold": 1.35466,
      "Value": 4.54875
    },
    {
      "MetricName": "RKOTCDPi",
      "Name": "tNpywJsP",
      "OccurrenceTime": 5,
      "Recovered": "Yes",
      "RecoveryTime": 8,
      "ResourceId": "WjPSUvSp",
      "ResourceType": "xTnHtABc",
      "Threshold": 1.33729,
      "Value": 3.37471
    }
  ],
  "RetCode": 0
}
```





