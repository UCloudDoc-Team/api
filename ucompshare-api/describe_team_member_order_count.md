# 获取团队成员订单总览 - DescribeTeamMemberOrderCount

## 简介

获取团队成员订单总览






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeTeamMemberOrderCount`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TeamId** | int | 团队ID |**Yes**|
| **VirtualCompanyId** | int | 团队虚拟账号ID |**Yes**|
| **BeginTime** | int | 起始时间，需使用时间戳 |**Yes**|
| **EndTime** | int | 结束时间，需使用时间戳，结束时间需大于起始时间 |**Yes**|
| **Regions** | string | 可用区 |No|
| **ResourceTypes** | string | 产品类型 |No|
| **OrderTypes** | string | 订单类型 |No|
| **ChargeTypes** | string | 付费方式 |No|
| **OrderStates** | string | 订单状态 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 订单数量 |**Yes**|
| **Amount** | string | 订单总金额 |**Yes**|
| **AmountReal** | string | 真实金额 |**Yes**|
| **AmountFree** | string | 赠送金额 |**Yes**|
| **AmountCoupon** | string | 代金券 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeTeamMemberOrderCount
&TeamId=4
&VirtualCompanyId=8
&BeginTime=5
&EndTime=6
&Regions=1
&ResourceTypes=fDcTadTG
&OrderTypes=iiSeryYx
&ChargeTypes=GtHjwzUH
&OrderStates=OS_FINISHED
```

### 响应示例
    
```json
{
  "Action": "DescribeTeamMemberOrderCountResponse",
  "Amount": 2,
  "AmountCoupon": 7,
  "AmountFree": 5,
  "AmountReal": 7,
  "RetCode": 0,
  "TotalCount": 2
}
```





