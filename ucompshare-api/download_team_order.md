# 下载团队订单 - DownloadTeamOrder

## 简介

下载团队订单






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DownloadTeamOrder`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TeamId** | int | 团队ID |**Yes**|
| **VirtualCompanyId** | int | 团队虚拟账号ID |No|
| **BeginTime** | int | 起始时间，需使用时间戳 |No|
| **EndTime** | int | 结束时间，需使用时间戳，结束时间需大于起始时间 |No|
| **OrderStates.N** | string | 订单状态 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **OrderNo** | string | 订单号 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **StartTime** | int | 开始时间 |**Yes**|
| **EndTime** | int | 结束时间 |**Yes**|
| **OrderType** | string | 订单类型 |**Yes**|
| **ResourceId** | string | 资源ID |**Yes**|
| **ResourceType** | string | 产品类型 |**Yes**|
| **ChargeType** | string | 计费方式 |**Yes**|
| **Amount** | string | 总金额 |**Yes**|
| **AmountReal** | string | 现金 |**Yes**|
| **AmountFree** | string | 赠金 |**Yes**|
| **AmountCoupon** | string | 代金券 |**Yes**|
| **VirtualCompanyId** | int | 成员ID |**Yes**|
| **RemarkName** | string | 成员备注 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DownloadTeamOrder
&TeamId=6
&VirtualCompanyId=3
&BeginTime=1
&EndTime=2
&OrderStates.n=OS_FINISHED
```

### 响应示例
    
```json
{
  "Action": "DownloadTeamOrderResponse",
  "Amount": "QHHaDZIU",
  "AmountCoupon": "bcsmuQeP",
  "AmountFree": "yRPDHbri",
  "AmountReal": "xcFFdYgs",
  "ChargeType": "numMnspC",
  "CreateTime": 4,
  "EndTime": 1,
  "OrderNo": "ZEHokwaI",
  "OrderType": "VOxIYlVP",
  "RemarkName": "EkhluebP",
  "ResourceId": "KnrvjBbi",
  "ResourceType": "dOmyIWUF",
  "RetCode": 0,
  "StartTime": 6,
  "VirtualCompanyId": 3
}
```





