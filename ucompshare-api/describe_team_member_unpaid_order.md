# 获取团队队员未支付订单 - DescribeTeamMemberUnpaidOrder

## 简介

获取团队队员未支付订单






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeTeamMemberUnpaidOrder`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BeginTime** | int | 起始时间，需使用时间戳 |**Yes**|
| **EndTime** | int | 结束时间，需使用时间戳，结束时间需大于起始时间 |**Yes**|
| **TeamId** | int | 团队ID |**Yes**|
| **VirtualCompanyId** | int | 团队虚拟账号ID |**Yes**|
| **Limit** | int | 返回数据长度，默认为25，最大100 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Regions.N** | int | 可用区 |No|
| **ResourceTypes.N** | int | 产品类型 |No|
| **OrderTypes.N** | string | 订单类型 |No|
| **ChargeTypes.N** | string | 付费方式 |No|
| **OrderStates.N** | string | 订单状态 |No|
| **OrderNos.N** | string | 订单号 |No|
| **ResourceIds.N** | string | 资源ID |No|
| **OrderBy** | string | 排序参数 |No|
| **OrderDir** | string | 排序方式 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **OrderInfos** | array[[*UnpaidOrderInfo*](#UnpaidOrderInfo)] | 订单详细信息 |**Yes**|
| **Total** | int | 总条数 |**Yes**|
| **Limit** | int | 分页大小 |**Yes**|
| **Offset** | int | 分页偏移 |**Yes**|

#### 数据模型


#### UnpaidOrderInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OrderNo** | string | 订单号 |No|
| **OrderType** | string | 订单类型 |No|
| **OrderState** | string | 订单状态 |No|
| **RegionId** | string | 可用区 |No|
| **ResourceType** | string | 产品类型 |No|
| **ChargeType** | string | 付费方式 |No|
| **Quantity** | string | 购买量 |No|
| **CreateTime** | int | 创建时间 |No|
| **UpdateTime** | int | 更新时间 |No|
| **StartTime** | int | 订单起始时间 |No|
| **EndTime** | int | 订单结束时间 |No|
| **TradeNo** | string | 交易号 |No|
| **ResourceId** | string | 资源短ID |No|
| **OriginalPrice** | string | 折扣率 |No|
| **OrderDetail** | array[[*UnpaidOrderDetail*](#UnpaidOrderDetail)] | 配置详情 |No|
| **Amount** | int | 金额 |No|

#### UnpaidOrderDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProductId** | int | 产品子类 |No|
| **Multiple** | int | 配置大小 |No|
| **BillItemId** | string | 计费对象的资源ID |No|
| **PurchaseValue** | int | 资源有效期 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeTeamMemberUnpaidOrder
&BeginTime=5
&EndTime=2
&TeamId=3
&VirtualCompanyId=8
&Limit=4
&Offset=5
&Regions.n=8
&ResourceTypes.n=5
&OrderTypes.n=BkWLeWrv
&ChargeTypes.n=fBDRylyB
&OrderStates.n=OS_FINISHED
&OrderNos.n=FgBUemPi
&ResourceIds.n=gauglGZh
&OrderBy=zZvBFIgY
&OrderDir=CDihfjac
```

### 响应示例
    
```json
{
  "Action": "DescribeTeamMemberUnpaidOrderResponse",
  "Limit": 3,
  "Offset": 3,
  "OrderInfos": [
    {
      "Amount": "pYtGapLk",
      "AmountCoupon": "VwGXBaSw",
      "AmountFree": "QgfuPfbG",
      "AmountReal": "BjVSWGiM",
      "ChargeType": "OombiUFY",
      "Count": 4,
      "CreateTime": 6,
      "EndTime": 8,
      "OrderDetail": [
        {
          "ProductName": "ijkuILzC",
          "Value": "NSpRANLd"
        }
      ],
      "OrderDetailOld": [
        {
          "ProductName": "OLyGCuzM",
          "Value": "PMKfyTKM"
        }
      ],
      "OrderNo": "VVOZjaxn",
      "OrderState": "OS_FINISHED",
      "OrderType": "BQAGZnRS",
      "OriginalPrice": "tTTXsArR",
      "ProjectName": "FgOMAAHS",
      "Quantity": "RUxJlnQS",
      "RegionId": "dQRbtCXI",
      "ResourceId": "ikVAUfSd",
      "ResourceTag": [
        {
          "KeyId": "kJwnwUxU",
          "Value": "EIGhgjUL"
        }
      ],
      "ResourceType": "fOFpTRCk",
      "SpotDiscount": "ZlfzuMuE",
      "StartTime": 2,
      "TradeNo": "fIZqYNBU",
      "UpdateTime": 9
    }
  ],
  "RetCode": 0,
  "Total": 4
}
```





