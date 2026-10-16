# 获取购买IP的价格 - DescribeBuyHighProtectGameIPPrice

## 简介

获取购买IP的价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeBuyHighProtectGameIPPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeBuyHighProtectGameIPPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |**Yes**|
| **ChargeType** | string | 付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按需付费(需开启权限); Trial |**Yes**|
| **Quantity** | int | 购买数量 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PremiumPrice** | float | 溢价 |**Yes**|
| **UnitPrice** | float | 单位价格 |**Yes**|
| **OriginalPremiumPrice** | float | 原溢价 |No|
| **OriginalUnitPrice** | float | 原单位价格 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetBuyGameIPPrice
&ResourceId="31db0df1-08c5-4547-8ccc-c2d99108403c"
&ChargeType="TypeFree"
&DefenceDDosBaseFlow=10
&Quantity=1
&IsRenew="No"
&UdpBlock=1
&LineType=TlSmsiRc
&AreaLine=EUtwioPD
&EngineRoom=myAGPVRd
```

### 响应示例
    
```json
{
  "Action": "DescribeBuyHighProtectGameIPPriceResponse",
  "OriginalPremiumPrice": 9.65833,
  "OriginalPrice": 9.24678,
  "OriginalUnitPrice": 5.95851,
  "PremiumPrice": "2000",
  "RetCode": 0,
  "UnitPrice": "1000"
}
```





