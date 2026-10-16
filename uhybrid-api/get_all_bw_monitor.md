# 获取所有监控数据 - GetAllBWMonitor

## 简介

获取所有监控数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAllBWMonitor)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAllBWMonitor`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目id |**Yes**|
| **BeginTime** | string | 开始时间戳 |**Yes**|
| **EndTime** | string | 结束时间戳 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*Allmonitors*](#Allmonitors)] | 返回数据 |**Yes**|

#### 数据模型


#### Allmonitors

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ItemId** | int | 监控id |**Yes**|
| **Monitors** | array[[*AllmonitorsData*](#AllmonitorsData)] | 监控数据 |**Yes**|

#### AllmonitorsData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BandId** | int | 带宽id |No|
| **BandName** | string | 带宽名称 |No|
| **Stats** | array[[*Stats*](#Stats)] | 带宽监控数据 |No|

#### Stats

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Value** | int | 数据值(bps) |**Yes**|
| **ValueTime** | int | 数据时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAllBWMonitor
&Region=ADcLBtAz
&Zone=ICrhStMV
&ProjectId=AflZXzes
&BeginTime=ebjWLqyH
&EndTime=VSMqvpvm
```

### 响应示例
    
```json
{
  "Action": "GetAllBWMonitorResponse",
  "Data": [
    {
      "Allmonitors": [
        {
          "BandId": 7,
          "BandName": "sfvqYSxu",
          "Stats": [
            {
              "Value": 5,
              "ValueTime": 2
            }
          ]
        }
      ],
      "ItemId": 5
    }
  ],
  "Message": "bIGVEyqT",
  "RetCode": 0
}
```





