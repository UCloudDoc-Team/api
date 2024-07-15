# 查询单路流流量 - GetULiveStreamTrafficData

## 简介

查询单路流流量






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveStreamTrafficData)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveStreamTrafficData`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **StartTime** | int | 流开始时间，时间戳格式 |**Yes**|
| **EndTime** | int | 流结束时间，时间戳格式，开始时间----结束时间，小于1天 |**Yes**|
| **Domain** | string | 拉流域名 |**Yes**|
| **StreamName** | string | 流名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalTraffic** | float | 查询时间段内总流量，单位GB |No|
| **TrafficDataList** | array[[*TrafficDataList*](#TrafficDataList)] | 流量列表 |No|

#### 数据模型


#### TrafficDataList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Traffic** | float | 流量，单位GB |No|
| **Time** | int | 时间，时间戳格式 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveStreamTrafficData
&ProjectId=XVsSWbiC
&StartTime=5
&EndTime=8
&Domain=tCxhlLtW
&StreamName=AzhqFzOD
```

### 响应示例
    
```json
{
  "Action": "GetULiveStreamTrafficDataResponse",
  "RetCode": 0,
  "TotalTraffic": 1.39572,
  "TrafficDataList": [
    {
      "Time": 4,
      "Traffic": 9.16168
    }
  ]
}
```





