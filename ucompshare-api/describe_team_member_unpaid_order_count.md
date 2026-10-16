# 获取团队成员未支付订单总览 - DescribeTeamMemberUnpaidOrderCount

## 简介

获取团队成员未支付订单总览






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeTeamMemberUnpaidOrderCount`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BeginTime** | int | 起始时间，需使用时间戳 |**Yes**|
| **EndTime** | int | 结束时间，需使用时间戳，结束时间需大于起始时间 |**Yes**|
| **TeamId** | int | 团队ID |**Yes**|
| **VirtualCompanyId** | int | 虚拟账号公司ID |**Yes**|
| **OrganizationId** | int | 组织ID |No|
| **ResourceIds** | string | 资源ID |No|
| **ResourceTypes** | int | 产品类型 |No|
| **OrderTypes.N** | string | 订单类型 |No|
| **OrderStates.N** | string | 订单状态 |No|
| **ChargeTypes.N** | string | 付费方式 |No|
| **Regions.N** | int | 可用区 |No|
| **TransactionNos.N** | string | 交易流水号 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 欠费订单数 |**Yes**|
| **Amount** | string | 欠费订单总金额 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeTeamMemberUnpaidOrderCount
&BeginTime=5
&EndTime=8
&TeamId=4
&VirtualCompanyId=4
&OrganizationId=3
&ResourceIds=HSQEhoDD
&ResourceTypes=7
&OrderTypes.n=kCDlnXsH
&OrderStates.n=fNBgaNQv
&ChargeTypes.n=QteimxeC
&Regions.n=1
&TransactionNos.n=rvBMiMHe
```

### 响应示例
    
```json
{
  "Action": "DescribeTeamMemberUnpaidOrderCountResponse",
  "Amount": 9,
  "RetCode": 0,
  "TotalCount": 4
}
```





