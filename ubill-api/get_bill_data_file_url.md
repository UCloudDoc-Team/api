# 生成账单数据文件下载的 url - GetBillDataFileUrl

## 简介

生成账单数据文件下载的 url






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
| **BillPeriod** | int | 账期（时间戳格式） |**Yes**|
| **BillType** | int | 账单类型，传 0 时获取账单总览报表，传 1 获取账单明细报表 |**Yes**|
| **PaidType** | int | 获取账单总览报表时，账单的支付状态，传 0 时获取待支付账单，传 1 时获取已支付账单。获取账单明细报表时该参数无效 |No|
| **RequireVersion** | string | 如需求其他语言版本的账单则使用此参数。默认中文。如 RequireVersion = "EN"，则提供英文版本账单。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **FileUrl** | string | 交易账单数据下载URL |No|
| **IsValid** | string | 生成的 URL是否有效，即有对应数据文件 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetBillDataFileUrl
&BillPeriod=1542681193
&BillType=0
&PaidType=1
&RequireVersion="EN"
```

### 响应示例
    
```json
{
  "Action": "GetBillDataFileUrlResponse",
  "FileUrl": "http://pre-channel-1.cn-sh2.ufileos.com/summary-bill-transaction-1-2018-11.xlsx?UCloudPublicKey=dsdaef121dadew23dads2222s\u0026Expires=1553497568\u0026Signature=seadfg3232ssdads1=",
  "IsValid": "yes",
  "RetCode": 0
}
```





