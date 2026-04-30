# 查询欠费订单汇总 - ListUnpaidOrderSummary

## 简介

按指定维度汇总查询欠费订单的统计数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUnpaidOrderSummary)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUnpaidOrderSummary`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StartTime** | int | 查询开始时间（Unix 时间戳，秒级），必填 |**Yes**|
| **EndTime** | int | 查询结束时间（Unix 时间戳，秒级），必填；必须大于 StartTime |**Yes**|
| **ResourceIds.N** | string | Key数组（多选，可选） |No|
| **OrderTypes** | int | 订单类型数组（多选，可选） |No|
| **ModelIds.N** | string | 模型ID数组（多选，可选） |No|
| **PricingUnits.N** | int | 计费单元数组（多选，可选） |No|
| **ChargeTypes.N** | int | 计费类型数组（多选，可选） |No|
| **PricingSkus.N** | string | 计费单元（SKU）列表（可选） |No|
| **Regions.N** | string | 地域列表（多选，可选），参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **OrganizationIds.N** | int | 组织ID列表（可选） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Summaries** | array[[*OrderSummaryItem*](#OrderSummaryItem)] | 欠费订单汇总列表 |**Yes**|

#### 数据模型


#### OrderSummaryItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |No|
| **PricingSKU** | string | 计费单元（SKU）名称 |No|
| **ModelID** | string | 模型ID |No|
| **ModelName** | string | 模型名称 |No|
| **PricingUnit** | int | 计费单位（计量单元） |No|
| **PricingUnitName** | string | 计费单位名称 |No|
| **OrderType** | int | 订单类型 |No|
| **OrderTypeDisplay** | string | 订单类型显示名 |No|
| **ChargeType** | int | 计费类型 |No|
| **Status** | int | 订单状态（2=已支付; 3=已撤销） |No|
| **StatusDisplay** | string | 订单状态显示名 |No|
| **ListPrice** | string | 列表价（原单价） |No|
| **DiscountPrice** | string | 折后单价 |No|
| **SumQuantity** | int | 总用量（原始值） |No|
| **SumQuantityDisplay** | string | 总用量显示（格式化后的字符串，千token和百万token会进行转换） |No|
| **SumOrderPrice** | string | 总订单金额（格式化后的字符串） |No|
| **SumOriginalPrice** | string | 总原价（格式化后的字符串） |No|
| **SumCashAccount** | string | 总现金账户扣款（仅已完成订单返回） |No|
| **SumStarCardAccount** | string | 总星力卡抵扣金额（仅已完成订单返回） |No|
| **SumBonusAccount** | string | 总赠金账户扣款（仅已完成订单返回） |No|
| **SumCoupon** | string | 总代金券抵扣（仅已完成订单返回） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUnpaidOrderSummary
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=cnSiQiol
&ResourceIds.N=AglVXrhh
&ModelIds.N=BQVSAjLU
&PricingUnits.N=3
&OrderTypes=1
&ChargeTypes.N=9
&StartTime=1
&EndTime=3
&PricingSkus.N=NFswTmQW
&Regions.N=uzZjhWLQ
&OrganizationIds.N=1
```

### 响应示例
    
```json
{
  "Action": "ListUnpaidOrderSummaryResponse",
  "Data": {},
  "RetCode": 0
}
```





