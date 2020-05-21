# 查看配额使用报表 - GetUFileReport

## 简介

查看配额使用报表

?> 说明：1. 参数EntTime和StartTime都是unix时间戳，必须保证 EndTime < StartTime，并且时间差小于一年。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUFileReport)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUFileReport`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **StartTime** | int | 查询开始时间 |**Yes**|
| **EndTime** | int | 查询结束时间 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UFileReportSet*](#UFileReportSet)] | 报表内容 参数见 UFileReportSet |No|

#### 数据模型


#### UFileReportSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 配额消费时间，unix时间戳，精确到日期 |No|
| **StorageVolume** | float | 配额消费当日使用的存储容量，单位：GB*天 |No|
| **DownloadTraffic** | float | 配额消费当日使用的下载流量，单位：GB |No|
| **RequestCount** | float | 配额消费当日使用的请求次数，单位：万次 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUFileReport
&Region=cn-bj2
&StartTime=1427558400
&EndTime=1427644799
```

### 响应示例
    
```json
{
  "Action": "GetUFileReportResponse",
  "DataSet": [
    {
      "DownloadTraffic": 10,
      "RequestCount": 10343,
      "StorageVolume": 32,
      "Time": 1427558400
    }
  ],
  "Retcode": 0
}
```





