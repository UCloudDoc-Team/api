# 获取账单总览 - ListUBillOverview

## 简介

账单总览。可按产品/项目/用户纬度获取某个账期内账单总览信息。

?> 当月账单总览一般存在一天延迟




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUBillOverview`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BillingCycle** | string | 账期，YYYY-MM格式，例如2022-02，只支持2018-05之后的查询 |**Yes**|
| **Dimension** | string | 账单维度, product 按产品聚合,project 按项目聚合，user 按子账号聚合	 |**Yes**|
| **HideUnpaid** | int | 是否显示已入账账单, 1 已入账, 0 待入账 (默认0 ) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 账单总览数据总数 |**Yes**|
| **TotalPaidAmount** | string | 已入账订单总额（已入账时显示） |No|
| **TotalPaidAmountReal** | string | 现金账户扣款总额	（已入账时显示） |No|
| **TotalUnpaidAmount** | string | 待入账订单总额（待入账时显示） |No|
| **Items** | array[[*BillOverviewItem*](#BillOverviewItem)] | 账单聚合数据 |**Yes**|

#### 数据模型


#### BillOverviewItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Dimension** | string | 账单维度, product 按产品维度聚合,project 按项目维度聚合，user 按子账号维度聚合 |**Yes**|
| **Amount** | string | 订单总金额 |**Yes**|
| **AmountCoupon** | string | 代金券抵扣（已入账时显示） |No|
| **AmountFree** | string | 赠送金额抵扣（已入账时显示） |No|
| **AmountReal** | string | 现金账户支付（已入账时显示） |No|
| **ProductCategory** | string | 产品分类	（账单维度按产品筛选时显示） |No|
| **ResourceType** | string | 产品类型	（账单维度按产品筛选时显示） |No|
| **ResourceTypeCode** | int | 产品类型代码（账单维度按产品筛选时显示） |No|
| **ProjectName** | string | 项目名称（账单维度按项目筛选时显示） |No|
| **UserEmail** | string | 账户邮箱（账单维度按子账号筛选时显示） |No|
| **UserName** | string | 账户名   （账单维度按子账号筛选时显示） |No|
| **UserDisplayName** | string | 账户昵称（账单维度按子账号筛选时显示） |No|
| **Admin** | int | 该账户是否为主账号，1 主账号，0 子账号（账单维度按子账号筛选时显示） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUBillOverview
&BillingCycle=2022-01
&Dimension=product
&HideUnpaid=0
```

### 响应示例
    
```json
{
  "Action": "ListUBillOverviewResponse",
  "Items": [
    {
      "Amount": "401.76",
      "Dimension": "product",
      "ProductCategory": "storage",
      "ResourceType": "ufs",
      "ResourceTypeCode": 112
    },
    {
      "Amount": "133.92",
      "Dimension": "product",
      "ProductCategory": "compute",
      "ResourceType": "USNAPSHOT",
      "ResourceTypeCode": 283
    }
  ],
  "RetCode": 0,
  "TotalCount": 2,
  "TotalUnpaidAmount": "535.68"
}
```





