# 获取团队订单 - DescribeTeamMemberOrder

## 简介

获取团队订单






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeTeamMemberOrder`                        | **Yes** |
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
| **OrderInfos** | array[[*OrderInfo*](#OrderInfo)] | 订单详细信息 |**Yes**|
| **Total** | int | 总条数 |**Yes**|
| **Limit** | int | 分页大小 |**Yes**|
| **Offset** | int | 分页偏移 |**Yes**|

#### 数据模型


#### OrderInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OrderNo** | string | 订单号 |No|
| **OrderType** | string | 订单类型 |No|
| **OrderState** | string | 订单状态 |No|
| **RegionId** | string | 可用区 |No|
| **ResourceType** | string | 产品类型 |No|
| **ChargeType** | string | 付费方式 |No|
| **Amount** | string | 订单金额 |No|
| **AmountReal** | string | 真实金额 |No|
| **AmountFree** | string | 赠金 |No|
| **AmountCoupon** | string | 优惠券金额 |No|
| **Quantity** | string | 购买量 |No|
| **Count** | int | 购买数量 |No|
| **CreateTime** | int | 创建时间 |No|
| **UpdateTime** | int | 更新时间 |No|
| **StartTime** | int | 订单起始时间 |No|
| **EndTime** | int | 订单结束时间 |No|
| **TradeNo** | string | 交易号 |No|
| **ResourceId** | string | 资源ID |No|
| **SpotDiscount** | string | 抢占式折扣，仅抢占式才展示 |No|
| **OriginalPrice** | string | 折扣率 |No|
| **ProjectName** | string | 项目名称 |No|
| **OrderDetail** | array[[*OrderDetailItem*](#OrderDetailItem)] | 配置详情 |No|
| **OrderDetailOld** | array[[*OrderDetailItem*](#OrderDetailItem)] | 原配置详情 |No|
| **ResourceTag** | array[[*ResourceTagItem*](#ResourceTagItem)] | 资源标识 |No|

#### OrderDetailItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProductName** | string | 产品名 |No|
| **Value** | string | 配置 |No|

#### ResourceTagItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **KeyId** | string | 标识名称 |No|
| **Value** | string | 标识信息 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeTeamMemberOrder
&BeginTime=9
&EndTime=7
&TeamId=1
&VirtualCompanyId=9
&Limit=4
&Offset=9
&Regions.n=5
&ResourceTypes.n=1
&OrderTypes.n=AbTUHMeP
&ChargeTypes.n=XJcUBXjr
&OrderStates.n=OS_FINISHED
&OrderNos.n=NNqkuozO
&ResourceIds.n=TyyUGavr
&OrderBy=yIdfVXoN
&OrderDir=ozJlRqIi
```

### 响应示例
    
```json
{
  "Action": "DescribeTeamMemberOrderResponse",
  "Limit": 9,
  "Offset": 3,
  "OrderInfos": [
    {
      "Amount": "WFRsGwBr",
      "AmountCoupon": "VYkjedVY",
      "AmountFree": "vJHtCyGz",
      "AmountReal": "vIfSvXam",
      "ChargeType": "bdQwoXcX",
      "Count": 5,
      "CreateTime": 3,
      "EndTime": 8,
      "OrderDetail": [
        {
          "ProductName": "WLlTsCKx",
          "Value": "DXpvzhIq"
        }
      ],
      "OrderDetailOld": [
        {
          "ProductName": "gyBBRsHF",
          "Value": "fFCMhdkf"
        }
      ],
      "OrderNo": "NcVMQYxZ",
      "OrderState": "OS_FINISHED",
      "OrderType": "uAOYKVPL",
      "OriginalPrice": "hJOEQZVN",
      "ProjectName": "qLpMIwIC",
      "Quantity": "tAgLIbmN",
      "RegionId": "suVWmfLR",
      "ResourceId": "BiSxqKxT",
      "ResourceTag": [
        {
          "KeyId": "XFoSrCaq",
          "Value": "crTwMPSh"
        }
      ],
      "ResourceType": "LQgiAvcM",
      "SpotDiscount": "urfzDLsI",
      "StartTime": 1,
      "TradeNo": "IDoFgAeG",
      "UpdateTime": 2
    }
  ],
  "RetCode": 0,
  "Total": 3
}
```





