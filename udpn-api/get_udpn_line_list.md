# 获取专线线路列表 - GetUDPNLineList

## 简介

获取当前支持的专线线路列表

?> 两个端点peer1和peer2之间的线路不一定支持，调用GetUDPNLineList查询支持线路



## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUDPNLineList)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUDPNLineList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string |  |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | DataSet中的元素个数 |**Yes**|
| **DataSet** | array[[*UDPNLineSet*](#UDPNLineSet)] | 当前支持的专线线路详细信息，详见UDPNLineSet |**Yes**|

#### 数据模型


#### UDPNLineSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LocalRegion** | string | 支持UDPN的地域之一，北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg, 华盛顿：us-ws, 洛杉矶：us-la， 东京：jpn-tky |**Yes**|
| **RemoteRegion** | string | 支持UDPN的地域之一，北京二：cn-bj2, 上海二：cn-sh2, 广东：cn-gd, 亚太： hk, 上海一：cn-sh1, 法兰克福：ge-fra, 新加坡：sg, 华盛顿：us-ws, 洛杉矶：us-la， 东京：jpn-tky |**Yes**|
| **BandwidthUpperLimit** | int | 线路带宽上限,单位 M |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUDPNLineList
&Region＝cn-sh2
&ProjectId=wziEviJS
```

### 响应示例
    
```json
{
  "Action": "GetUDPNLineListResponse",
  "DataSet": [
    {
      "BandwidthUpperLimit": 1000,
      "LocalRegion": "cn-bj2",
      "RemoteRegion": "cn-gd"
    },
    {
      "BandwidthUpperLimit": 1000,
      "LocalRegion": "cn-gd",
      "RemoteRegion": "hk"
    },
    {
      "BandwidthUpperLimit": 1000,
      "LocalRegion": "cn-bj2",
      "RemoteRegion": "hk"
    }
  ],
  "RetCode": 0,
  "TotalCount": 3
}
```





