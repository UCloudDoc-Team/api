# 查询已完成订单明细 - ListPaidOrders

## 简介

查询已完成（已支付）的订单明细列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListPaidOrders)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListPaidOrders`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StartTime** | int | 查询开始时间（Unix 时间戳，秒级）。与 `EndTime` 同时提供时启用自定义周期查询；EndTime 必须大于 StartTime |**Yes**|
| **EndTime** | int | 查询结束时间（Unix 时间戳，秒级）。需与 `StartTime` 同时提供 |**Yes**|
| **Page** | int | 页码，从1开始 |**Yes**|
| **PageSize** | int | 每页数量（最小10，最大100） |**Yes**|
| **ResourceIds.N** | string | 资源ID数组（多选，可选） |No|
| **ModelIds.N** | string | 模型ID数组（多选，可选） |No|
| **PricingUnits.N** | int | 计费单位数组（多选，可选） |No|
| **OrderTypes.N** | int | 订单类型数组（多选，可选） |No|
| **PricingSkus.N** | string | 计费 SKU 列表（可选） |No|
| **ProductCodes.N** | string | 产品类型列表（多选，可选），枚举值：`modelverse`、`sandbox` |No|
| **Regions.N** | string | 地域列表（多选，可选），参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **OrganizationIds.N** | int | 组织ID列表（可选） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Page** | int | 当前页码 |**Yes**|
| **PageSize** | int | 每页数量 |No|
| **Total** | int | 总记录数 |No|
| **Orders** | array[[*OrderItemDetail*](#OrderItemDetail)] | 订单列表 |No|

#### 数据模型


#### OrderItemDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |No|
| **ProductCode** | string | 产品类型 |No|
| **ProductCodeDisplay** | string | 产品类型显示名 |No|
| **StarCardAccount** | string | 星力卡抵扣金额 |No|
| **OrderNo** | string | 订单号 |No|
| **CompanyID** | int | 公司id |No|
| **OrganizationID** | int | 项目ID |No|
| **OrganizationName** | string | 项目名称 |No|
| **UserEmail** | string | 用户邮箱 |No|
| **ChargeType** | int | 计费类型 |No|
| **ChargeTypeDisplay** | string | 计费类型显示名 |No|
| **Channel** | int | 渠道 |No|
| **Currency** | string | 币种（如：CNY、USD） |No|
| **CurrencyDisplay** | string | 币种显示名 |No|
| **ResourceID** | string | 资源ID |No|
| **ModelID** | string | 模型ID |No|
| **ModelName** | string | 模型名称 |No|
| **OrderType** | int | 订单类型 |No|
| **OrderTypeDisplay** | string | 订单类型显示名 |No|
| **PricingSKU** | string | 计费单元（SKU）名称 |No|
| **Quantity** | int | 用量 |No|
| **QuantityDisplay** | string | 用量显示（含单位） |No|
| **PricingUnit** | int | 计费单位（计量单元） |No|
| **PricingUnitDisplay** | string | 计费单位显示名（如：千Token、张、秒） |No|
| **ListPrice** | string | 列表价（原单价） |No|
| **DiscountPrice** | string | 折后价（折后单价） |No|
| **OrderTotalPrice** | string | 订单总额 |No|
| **OriginalPrice** | string | 原价 |No|
| **Status** | int | 订单状态 |No|
| **StatusDisplay** | string | 订单状态显示名 |No|
| **StartTime** | int | 开始计费时间（Unix 时间戳，秒级） |No|
| **EndTime** | int | 结束计费时间（Unix 时间戳，秒级） |No|
| **PaidTime** | int | 支付完成时间（Unix 时间戳，秒级） |No|
| **CashAccount** | string | 现金账户扣款金额 |No|
| **BonusAccount** | string | 赠金账户扣款金额 |No|
| **Coupon** | string | 代金券抵扣金额 |No|
| **UnpaidOrderNo** | string | 欠费订单号 |No|
| **RegionDisplay** | string | 地域显示名 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListPaidOrders
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=IDsbKUjo
&Page=6
&PageSize=9
&ResourceIds.N=AeFSrUzZ
&ModelIds.N=kfUPLHaN
&PricingUnits.N=4
&OrderTypes.N=1
&StartTime=4
&EndTime=5
&PricingSkus.N=ueOIxKoz
&ProductCodes.N=PcpOcCXZ
&Regions.N=IVigjwbh
&OrganizationIds.N=8
```

### 响应示例
    
```json
{
  "Action": "ListPaidOrdersResponse",
  "Data": {},
  "Orders": [
    {
      "BonusAccount": "AgXuWXUE",
      "CashAccount": "dvsJvKeb",
      "Channel": 5,
      "ChargeType": 8,
      "ChargeTypeDisplay": "BzeIdKsp",
      "CompanyID": 5,
      "Coupon": "bYZilSNV",
      "CreditAccount": "ddqZVbbL",
      "Currency": "OcSKWFHV",
      "CurrencyDisplay": "JfLOksHY",
      "DiscountPrice": "yqGjZsVq",
      "EndTime": 1,
      "ListPrice": "QoIypZbG",
      "ModelID": "KdJndPFe",
      "ModelName": "PuNopUfo",
      "OrderNo": "dPfZKSHW",
      "OrderTotalPrice": "dKQVVWHo",
      "OrderType": 6,
      "OrderTypeDisplay": "mhpQYHbO",
      "OrganizationID": 5,
      "OrganizationName": "TsIIjvmL",
      "OriginalPrice": "UElWQRCf",
      "PaidTime": 9,
      "PricingItemID": 5,
      "PricingSKU": "kGHeOOsB",
      "PricingUnit": 5,
      "PricingUnitDisplay": "mBfpOMCm",
      "Quantity": 9,
      "QuantityDisplay": "nnnhBEHV",
      "ResourceID": "nhULypVv",
      "ResourceType": 2,
      "ResourceTypeDisplay": "QGWVsrLb",
      "StartTime": 3,
      "Status": 4,
      "StatusDisplay": "AcQIUtuY",
      "UnpaidOrderNo": "qBHrxRBp",
      "UserEmail": "OOFVHQds"
    }
  ],
  "PageSize": 3,
  "RetCode": 0,
  "Total": 6
}
```





