# 获取弹性IP带宽改动价格 - GetEIPUpgradePrice

## 简介

获取弹性IP带宽改动价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetEIPUpgradePrice)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetEIPUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **EIPId** | string | 弹性IP的资源ID |**Yes**|
| **Bandwidth** | int | 弹性IP的外网带宽, 单位为Mbps, 范围 [1-800] |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 调整带宽后的EIP价格, 单位为"元", 如需退费此处为负值 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetEIPUpgradePrice
&Region=cn-bj2
&Bandwidth=40
&EIPId=eip-XXX
```

### 响应示例
    
```json
{
  "Action": "GetEIPUpgradePriceResponse",
  "Price": 4.6,
  "PurchaseValue": 1530374400,
  "Request_uuid": "ccf83d8b-5888-4940-8d18-XXXXX",
  "RetCode": 0
}
```





