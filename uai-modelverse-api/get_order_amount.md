# 查询订单汇总统计 - GetOrderAmount

## 简介

查询指定条件下订单的金额汇总及数量统计






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetOrderAmount)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetOrderAmount`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StartTime** | int | 查询开始时间（Unix 时间戳，秒级）。需与 `EndTime` 同时提供，最大查询跨度 366 天 |**Yes**|
| **EndTime** | int | 查询结束时间（Unix 时间戳，秒级）。需与 `StartTime` 同时提供 |**Yes**|
| **ResourceIds.N** | string | 资源ID列表（可选） |No|
| **ModelIds.N** | string | 模型ID列表（可选） |No|
| **PricingUnits.N** | int | 计费单位列表（可选） |No|
| **PricingSkus.N** | string | 计费单元（SKU）列表（可选） |No|
| **ProductCodes.N** | string | 产品类型列表（可选），枚举值：`modelverse`、`sandbox` |No|
| **OrderTypes.N** | int | 订单类型列表（可选） |No|
| **Regions.N** | string | 地域列表（可选），参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **OrganizationIds.N** | string | 组织ID列表（可选） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalOrderAmount** | string | 订单总额（所有订单的总金额） |**Yes**|
| **PaidAmount** | string | 已支付金额 |No|
| **UnpaidAmount** | string | 待支付金额 |No|
| **CashAmount** | string | 现金账户总金额 |No|
| **BonusAmount** | string | 赠金账户总金额 |No|
| **CouponAmount** | string | 代金券抵扣总额 |No|
| **StarCardAmount** | string | 星力卡抵扣总金额 |No|
| **OrderCount** | int | 订单总数 |No|
| **PaidCount** | int | 已支付订单数 |No|
| **UnpaidCount** | int | 待支付订单数量 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetOrderAmount
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=xBjqWlgq
&ResourceIds.N=YUhHIvbF
&ModelIds.N=YLZoVxpX
&PricingUnits.N=4
&OrderTypes.N=6
&StartTime=2
&EndTime=7
&PricingSkus.N=ZvSMEZfo
&ProductCodes.N=GQiNWIED
&Regions.N=dOnMCcfY
&OrganizationIds.N=HFhMPcol
&Regions.N=ainUEQqh
&OrganizationIds.N=BZLMCvrq
```

### 响应示例
    
```json
{
  "Action": "GetOrderAmountResponse",
  "BonusAmount": "wqQkjckV",
  "CashAmount": "Hsbcqacs",
  "CouponAmount": "ZRcRUuyv",
  "Data": {},
  "OrderCount": 7,
  "PaidAmount": "SiiWorjy",
  "PaidCount": 8,
  "RetCode": 0,
  "StarCardAmount": "fEuXwTFD",
  "UnpaidAmount": "TaOEmaIs",
  "UnpaidCount": 5
}
```





