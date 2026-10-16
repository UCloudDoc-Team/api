# 获取共享带宽价格 - DescribeShareBandwidthPrice

## 简介

获取共享带宽价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeShareBandwidthPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeShareBandwidthPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ChargeType** | string | 付费方式, 预付费:Year 按年,Month 按月,Dynamic 按需; |**Yes**|
| **ShareBandwidth** | int | 共享带宽值 |**Yes**|
| **Quantity** | int | 购买数量 |No|
| **OperatorName** | string | 香港地域支持：BGPPro和International。其他地域无需填写该字段 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalPrice** | int | 共享带宽总价格 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeShareBandwidthPrice
&ChargeType=aIPIafej
&ShareBandwidth=6
&Quantity=1
&ShareBandwidthGuarantee=6
```

### 响应示例
    
```json
{
  "Action": "DescribeShareBandwidthPriceResponse",
  "RetCode": 0,
  "TotalPrice": 4
}
```





