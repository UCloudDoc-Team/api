# 开通共享带宽 - AllocateShareBandwidth

## 简介

开通共享带宽






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AllocateShareBandwidth)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AllocateShareBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 |No|
| **Name** | string | 共享带宽名字 |**Yes**|
| **ChargeType** | string | 付费方式:Year 按年,Month 按月,Dynamic 按时; |**Yes**|
| **ShareBandwidth** | int | 共享带宽值 |**Yes**|
| **Quantity** | int | 购买时长 |No|
| **IPVersion** | string | 共享带宽类型，IPv4或者IPv6，不传默认IPv4 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ShareBandwidthId** | string | 共享带宽资源Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AllocateShareBandwidth
&Region=cn-bj2
&ShareBandwidth=20
&ChargeType=Month
&Name=sharebwname
&BwType=XnbjjTdZ
```

### 响应示例
    
```json
{
  "Action": "AllocateShareBandwidthResponse",
  "Request_uuid": "94053674-0160-40f2-8981-XXXXXXX",
  "RetCode": 0,
  "ShareBandwidthId": "mdfMzyBm"
}
```





