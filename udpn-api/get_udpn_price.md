# 获取 UDPN 价格 - GetUDPNPrice

## 简介

获取 UDPN 价格

?> 两个端点peer1和peer2之间的线路不一定支持，调用GetUDPNLineList查询支持线路




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUDPNPrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUDPNPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |No|
| **Peer1** | string | 专线可用区1，支持地域：北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg, 洛杉矶：us-la， 华盛顿：us-ws， 东京：jpn-tky |**Yes**|
| **Peer2** | string | 专线可用区2，支持地域：北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg, 洛杉矶：us-la， 华盛顿：us-ws， 东京：jpn-tky |**Yes**|
| **Bandwidth** | int | 带宽信息 |**Yes**|
| **ChargeType** | string | 计费类型 |No|
| **Quantity** | int | 购买时长 |No|
| **PayMode** | string | PayMode，枚举值，Bandwidth：带宽；Traffic：流量  默认不填写：带宽 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PurchaseValue** | int | 资源有效期 unix 时间戳 |**Yes**|
| **Price** | float | 专线价格 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUDPNPrice
&Region=cn-bj2
&Peer1=cn-bj2
&Peer2=cn-gd
&Bandwidth=2
&ChargeType=Month
&Quantity=1
&PayMode=qvLqhheB
&PayMode=xaMcAgsM
```

### 响应示例
    
```json
{
  "Action": "GetUDPNPriceResponse",
  "Price": 200,
  "PurchaseValue": 1511491209,
  "RetCode": 0
}
```





