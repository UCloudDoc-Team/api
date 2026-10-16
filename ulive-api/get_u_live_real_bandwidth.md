# 获取实时带宽 - GetULiveRealBandwidth

## 简介

实时带宽查询接口






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveRealBandwidth)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveRealBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **StartTime** | int | 起始时间点，秒级时间戳 |**Yes**|
| **EndTime** | int | 结束时间点，秒级时间戳，时间范围不超过两个小时 |**Yes**|
| **DomainList.N** | string | 拉流域名列表，不超过 100 个域名。使用ParameterName.n的形式，如：Instance.0、Instance.1 …… Instance.n，n是自然数 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RequestId** | string | 请求 ID，会被字节侧打印出来，用于问题排查 |No|
| **ErrorCode** | int | 错误码，0 表示调用成功，非 0 表示异常 |No|
| **ErrorMessage** | string | 错误信息 |No|
| **BandwidthDetailList** | array[[*BandwidthDetail*](#BandwidthDetail)] | 带宽详情列表 |No|

#### 数据模型


#### BandwidthDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 拉流域名 |**Yes**|
| **BandwidthInfoList** | array[[*BandwidthInfoList*](#BandwidthInfoList)] | 带宽信息列表 |**Yes**|

#### BandwidthInfoList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Value** | float | 带宽，单位：Mbps，保留两位小数 |**Yes**|
| **Time** | int | 带宽对应的秒级时间戳，19:55 ～ 20:00 的计费带宽则返回 19:55 的时间戳 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveRealBandwidth
&ProjectId=ncuLDtsR
&StartTime=5
&EndTime=8
&DomainList.n=zltsXQwO
```

### 响应示例
    
```json
{
  "Action": "GetULiveRealBandwidthResponse",
  "BandwidthDetailList": [
    {
      "BandwidthInfoList": [
        {
          "Time": 1,
          "Value": 6.34545
        }
      ],
      "Domain": "qPsAIRKD"
    }
  ],
  "ErrorCode": 5,
  "ErrorMessage": "cgJvpjQd",
  "RequestId": "yeFDkbou",
  "RetCode": 0
}
```





