# 获取负载均衡价格 - GetNetworkLoadBalancerPrice

## 简介

获取负载均衡价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNetworkLoadBalancerPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNetworkLoadBalancerPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ChargeType** | string | 付费模式<br />限定枚举值："Year" / "Month"/ "Dynamic"<br />默认获取三种价格 |No|
| **PayMode** | string | 负载均衡实例计费方式<br />限定枚举值："Instance" / "LCU"<br />默认值："Instance" |No|
| **Quantity** | int | 购买时长<br />按小时购买（Dynamic）时无需此参数。月付时，此参数传 0，代表了购买至月末<br />默认 1 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Prices** | array[[*PriceDetail*](#PriceDetail)] |  |**Yes**|

#### 数据模型


#### PriceDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 负载均衡付费方式 |No|
| **Price** | float | 购买负载均衡的实际价格，单位“元” |No|
| **CustomPrice** | float | 用户折后价，单位“元”。CustomPrice=OriginalPrice*用户折扣 |No|
| **OriginalPrice** | float | 购买负载均衡的原价，单位“元”	 |No|
| **PurchaseValue** | int | 资源有效期，以Unix Timestamp表示 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNetworkLoadBalancerPrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=nGnZnGNf
&ChargeType=FftdAOgA
&PayMode=WVsBoyws
&Quantity=PNtsJWRQ
```

### 响应示例
    
```json
{
  "Action": "GetNetworkLoadBalancerPriceResponse",
  "Prices": [
    {
      "ChargeType": "YMQVkefZ",
      "CustomPrice": 2.94455,
      "OriginalPrice": 3.55214,
      "Price": 4.19143,
      "PurchaseValue": 6
    }
  ],
  "RetCode": 0
}
```





