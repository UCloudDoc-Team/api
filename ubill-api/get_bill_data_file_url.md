# 生成账单数据文件下载的 url - GetBillDataFileUrl

## 简介

生成账单数据文件下载的 url，包含三类文件，1. 已支付总览账单(支持CSV和PDF,从2023年03月开始支持PDF)；2. 未支付总览文件(支持CSV，只有当月账期可以查看)；3 账单详情文件(支持CSV)。           备注：文件生成有延迟，若返回值 IsValid=‘no’，需要使用者发起重试。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetBillDataFileUrl`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BillType** | int | 账单类型，枚举值：<br /><br /> > 0: 账单总览报表; <br /><br /> > 1: 账单明细报表 |**Yes**|
| **BillingCycle** | string | 账期: YYYY-MM格式的字符串，例如 ”2021-08“ |**Yes**|
| **BillPeriod** | int | 账期: 时间戳格式，已弃用，请使用BillingCycle |No|
| **PaidType** | int | 账单支付状态，  (获取账单明细报表，不需要填写该参数)，枚举值：<br /><br /> > 0: 0待支付总览账单(只支持当前月份的账期);<br /><br /> > 1: 已支付账单总览 |No|
| **RequireVersion** | string | 账单语言版本，枚举值：<br /><br /> > ”“: 默认中文;<br /><br /> > ”EN“: 英文版本 |No|
| **Version** | string | 文件版本，固定值"v1"。 |No|
| **Format** | string | 文件格式，枚举值：<br /><br /> > ”csv“: csv格式;<br /><br /> > ”pdf“: pdf格式(已支付总览文件 从2023年03月开始支持PDF) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **FileUrl** | string | 交易账单文件下载URL |No|
| **IsValid** | string | 是否有对应数据文件。(该参数返回no，表示文件正在生成中，需要用户发起重试获取。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetBillDataFileUrl
&BillingCycle="2021-12"
&BillType=1
&PaidType=1
&RequireVersion="EN"
&Version="v1"
&Format=fzBtbbkp
&BillPeriod=6
&BillPeriod=7
```

### 响应示例
    
```json
{
  "Action": "GetBillDataFileUrlResponse",
  "FileUrl": "https://channel-1.cn-bj.ufileos.com/order-detail-1-2021-12-en.v1.csv?UCloudPublicKey=TOKEN_6ecddc1d-96c3-49a0-bfa6-ef1621f075fa\u0026Expires=1640163358\u0026Signature=0IfhSgJl2SrYbMl6bAnNW7kmhYw=",
  "IsValid": "yes",
  "RetCode": 0
}
```





