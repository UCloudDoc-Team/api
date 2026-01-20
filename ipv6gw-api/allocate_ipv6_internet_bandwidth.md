# 分配ipv6公网带宽 - AllocateIpv6InternetBandwidth

## 简介

分配ipv6公网带宽






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AllocateIpv6InternetBandwidth)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AllocateIpv6InternetBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Ipv6AddressId** | string | Ipv6地址ID |**Yes**|
| **Bandwidth** | int | 出向带宽峰值。带宽值范围[1, 2000] |**Yes**|
| **PayMode** | string | 付费模式；默认值："Bandwidth"；<br />枚举值：<br />"Bandwidth" -> 带宽计费 |No|
| **ChargeType** | string | 付费方式；默认值："Month";<br />枚举值：<br />"Dynamic" -> 按时付费，<br />"Month" -> 月付，<br />"Year" ->年付，<br />"Day" -> 天付 |No|
| **VPCId** | string | vpcId；与Ipv6GatewayId二选一必填 |No|
| **Ipv6GatewayId** | string | ipv6网关ID；与VPCId二选一必填 |No|
| **Name** | string | 资源名称；默认值："Ipv6InternetBandwidth" |No|
| **Tag** | string | 业务组名称；默认值："Default" |No|
| **Remark** | string | 备注 |No|
| **Quantity** | int | 购买数量；默认值：1。 月付时，此参数传0，代表了购买至月末。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InternetBandwidthId** | string | 开通公网带宽后，对应的公网带宽实例 ID。 |**Yes**|
| **Ipv6Address** | string | ipv6地址 |No|
| **Ipv6AddressId** | string | ipv6地址ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AllocateIpv6InternetBandwidth
&Region=rus-mosc
&ProjectId=org-XXXXX
&Ipv6AddressId=ipv6-XXXXX
&Name=Ipv6InternetBandwidth
&Tag=Default
&Remark=Test
&Bandwidth=10
&ChargeType=Month
&PayMode=Bandwidth
&VPCId=uvnet-XXXXX
&Ipv6GatewayId=ipv6gw-XXXXX
&Quantity=1
```

### 响应示例
    
```json
{
  "Action": "AllocateIpv6InternetBandwidthResponse",
  "InternetBandwidthId": "ipv6bw-XXXXX",
  "Ipv6Address": "X:X:X:X:X:X:X:X",
  "Ipv6AddressId": "ipv6-XXXXX",
  "RetCode": 0
}
```





