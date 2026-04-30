# 查询已完成订单汇总 - ListPaidOrderSummary

## 简介

按指定维度汇总查询已完成（已支付）订单的统计数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListPaidOrderSummary)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListPaidOrderSummary`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StartTime** | int | 查询开始时间（Unix 时间戳，秒级），必填 |**Yes**|
| **EndTime** | int | 查询结束时间（Unix 时间戳，秒级），必填；必须大于 StartTime |**Yes**|
| **ResourceIds.N** | string | 资源ID数组（多选，可选） |No|
| **ModelIds.N** | string | 模型ID数组（多选，可选) |No|
| **PricingUnits.N** | int | 计费单位数组（多选，可选） |No|
| **OrderTypes.N** | int | 订单类型数组（多选，可选） |No|
| **ChargeTypes.N** | int | 计费类型数组（多选，可选） |No|
| **PricingSkus.N** | string | 计费单元（SKU）列表（可选） |No|
| **ProductCodes.N** | string | 产品类型列表（多选，可选），枚举值：`modelverse`、`sandbox` |No|
| **Regions.N** | string | 地域列表（多选，可选），参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **OrganizationIds.N** | int | 组织ID列表（可选） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Summaries** | array[[*OrderSummaryItem*](#OrderSummaryItem)] | 已完成订单汇总列表 |**Yes**|

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
https://api.ucloud.cn/?Action=ListPaidOrderSummary
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=pRaRcTyR
&ResourceIds=GcNNUFXd
&ModelIds=kZzfEgJH
&PricingUnits=xJSAmIHa
&OrderTypes=oxWOAWBD
&ChargeTypes=jJHlYEWQ
&StartTime=1
&EndTime=rpsXDfTb
&ResourceIds=MBRJGfJr
&ModelIds=HzLyYzfC
&PricingUnits=MvBqNaFn
&OrderTypes=HMrUmfFX
&ChargeTypes=MWUTHbrb
&StartTime=5
&EndTime=7
&ResourceIds.N=GtZdlexq
&ModelIds.N=dufLMhYc
&PricingUnits.N=3
&OrderTypes.N=3
&ChargeTypes.N=3
&StartTime=3
&EndTime=3
&ResourceIds.N=Lthksvru
&ModelIds.N=eQNoCsux
&PricingUnits.N=9
&OrderTypes.N=8
&ChargeTypes.N=7
&StartTime=6
&EndTime=5
&PricingSkus.N=vqcXxipb
&ProductCodes.N=TCBxiHlp
&Regions.N=QwmZlhIn
&OrganizationIds.N=dAhmKEcI
&Regions.N=AaPOmFNz
&OrganizationIds.N=6
```

### 响应示例
    
```json
{
  "Action": "ListPaidOrderSummaryResponse",
  "Data": {},
  "RetCode": 0
}
```





