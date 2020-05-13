# 获取VPN价格 - GetVPNGatewayPrice

## 简介

获取VPN价格





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetVPNGatewayPrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetVPNGatewayPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **Grade** | string | VPN网关规格。枚举值，包括：标准型：Standard，增强型：Enhanced。 |**Yes**|
| **ChargeType** | string | 付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按需付费(需开启权限); 默认为获取三种价格 |No|
| **Quantity** | int | 购买时长, 默认: 1 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*VPNGatewayPriceSet*](#VPNGatewayPriceSet)] | 获取的VPN网关价格信息列表，每项参数详见 VPNGatewayPriceSet |No|

#### 数据模型


#### VPNGatewayPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | VPN网关付费方式 |No|
| **Price** | float | VPN网关价格, 单位"元" |No|
| **PurchaseValue** | int | 资源有效期, 以Unix Timestamp表示 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetVPNGatewayPrice
&Region=cn-sh2
&ProjectId=org-XXXXXX
&Grade=Standard
&ChargeType=Month
&Quantity=1
```

### 响应示例
    
```json
{
  "Action": "GetVPNGatewayPriceResponse",
  "PriceSet": [
    {
      "ChargeType": "Dynamic",
      "Price": 0.19,
      "PurchaseValue": 1530080647
    },
    {
      "ChargeType": "Month",
      "Price": 90,
      "PurchaseValue": 1532669047
    },
    {
      "ChargeType": "Year",
      "Price": 900,
      "PurchaseValue": 1561613047
    }
  ],
  "RetCode": 0
}
```





