# 获取账户余额 - GetBalance

## 简介

获取账户余额






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetBalance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AccountInfo** | array[[*AccountInfo*](#AccountInfo)] | 账户余额信息 |**Yes**|

#### 数据模型


#### AccountInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AmountFreeze** | float | 冻结账户金额 |No|
| **AmountCredit** | string | 信用账户余额 |No|
| **AmountFree** | string | 赠送账户余额 |No|
| **Amount** | string | 账户余额 |No|
| **AmountAvailable** | string | 账户可用余额 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetBalance
```

### 响应示例
    
```json
{
  "Action": "GetBalanceResponse",
  "Amount": 3.99529,
  "AmountCredit": "yAMrPpUv",
  "AmountFree": 1.18659,
  "AmountFreeze": 6.51374,
  "RetCode": 0
}
```





