# 分配 UDPN 专线 - AllocateUDPN

## 简介

分配一条 UDPN 专线

?> 两个端点peer1和peer2之间的线路不一定支持，调用GetUDPNLineList查询支持线路




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AllocateUDPN)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AllocateUDPN`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Peer1** | string | 专线可用区1，支持地域：北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg,  洛杉矶：us-la， 华盛顿：us-ws， 东京：jpn-tky |**Yes**|
| **Peer2** | string | 专线可用区2，支持地域：北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg,  洛杉矶：us-la， 华盛顿：us-ws， 东京：jpn-tky |**Yes**|
| **Bandwidth** | int | 带宽 |**Yes**|
| **ChargeType** | string | 计费类型，枚举值为： Year，按年付费； Month，按月付费； Dynamic，按需付费 |No|
| **Quantity** | int | 计费时长，默认 1 |No|
| **PayMode** | string | 计费模式. 枚举值："Traffic", 流量计费模式; 否则 带宽计费模式； |No|
| **CouponId** | string | 代金劵 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UDPNId** | string | 资源名称 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AllocateUDPN
&Peer1=cn-bj2
&Peer2=cn-gd
&Bandwidth=2
&ChargeType=Month
&Quantity=1
&PayMode=qyuDFbNT
```

### 响应示例
    
```json
{
  "Action": "AllocateUDPNResponse",
  "RetCode": 0,
  "UDPNId": "udpn-XXXXXX"
}
```





