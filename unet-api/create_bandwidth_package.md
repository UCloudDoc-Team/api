# 创建带宽包 - CreateBandwidthPackage

## 简介

为非共享带宽模式下, 已绑定资源实例的带宽计费弹性IP附加临时带宽包





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateBandwidthPackage)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateBandwidthPackage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Bandwidth** | int | 带宽大小(单位Mbps), 取值范围[2,800] (最大值受地域限制) |**Yes**|
| **EIPId** | string | 所绑定弹性IP的资源ID |**Yes**|
| **TimeRange** | int | 带宽包有效时长, 取值范围为大于0的整数, 即该带宽包在EnableTime到 EnableTime+TimeRange时间段内生效 |**Yes**|
| **EnableTime** | int | 生效时间, 格式为 Unix timestamp, 默认为立即开通 |No|
| **CouponId** | string | 代金券ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BandwidthPackageId** | string | 所创建带宽包的资源ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateBandwidthPackage
&Region=cn-bj2
&EIPId=eip-vuxqym
&Bandwidth=200
&EnableTime=1430986009
&TimeRange=1
```

### 响应示例
    
```json
{
  "Action": "CreateBandwidthPackageResponse",
  "BandwidthPackageId": "bwpack-rybftq",
  "RetCode": 0
}
```





