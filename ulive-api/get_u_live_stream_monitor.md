# 获取流监控 - GetULiveStreamMonitor

## 简介

对一路流监控(帧率，码率，带宽，在线人数)






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveStreamMonitor)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveStreamMonitor`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 流开始时间,时间戳格式 |**Yes**|
| **Domain** | string | 域名 |**Yes**|
| **StreamName** | string | 流名 |**Yes**|
| **EndTime** | int | 结束时间，时间戳格式，不填则为当前时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MonitorInfo** | array[[*MonitorInfo*](#MonitorInfo)] | 在线流监控列表 |**Yes**|

#### 数据模型


#### MonitorInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间点 |No|
| **Bitrate** | string | 码率 |No|
| **Framerate** | string | 帧率 |No|
| **Bandwidth** | string | 带宽 |No|
| **OnlineValue** | string | 在线人数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveStreamMonitor
&ProjectId=TlwRlOMW
&BeginTime=9
&Domain=LYUSruXs
&StreamName=vMhhUFRK
&EndTime=9
```

### 响应示例
    
```json
{
  "Action": "GetULiveStreamMonitorResponse",
  "MonitorInfo": [
    {
      "Bandwidth": "zUPQFedj",
      "Bitrate": "dYoSLxOb",
      "Framerate": "rcLJbRoL",
      "OnlineValue": "UmbardTG",
      "Time": 4
    }
  ],
  "RetCode": 0
}
```





