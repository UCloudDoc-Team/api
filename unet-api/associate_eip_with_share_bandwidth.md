# 将EIP加入共享带宽 - AssociateEIPWithShareBandwidth

## 简介

将EIP加入共享带宽






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AssociateEIPWithShareBandwidth)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AssociateEIPWithShareBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。<br /> |No|
| **EIPIds.N** | string | 要加入共享带宽的EIP的资源Id |**Yes**|
| **ShareBandwidthId** | string | 共享带宽ID |**Yes**|
| **IPVersion** | string | 共享带宽类型，IPv4或者IPv6，不传默认IPv4 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AssociateEIPWithShareBandwidth
&Region=cn-bj2
&EIPIds.0=eip-XXXXX
&ShareBandwidthId=bwshare-XXXXX
&BwType=tcsRSDBP
&IPVersion=iUnPUHzo
```

### 响应示例
    
```json
{
  "Action": "AssociateEIPWithShareBandwidthResponse",
  "Request_uuid": "d4dde503-0b50-451d-943b-XXXXXXXXX",
  "RetCode": 0
}
```





