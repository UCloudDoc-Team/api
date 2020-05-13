# 查询配额支付价格 - GetUFileQuotaPrice

## 简介

根据UFile的购买配额，查询需要支付的价格。

?> 说明：如果StorageVolume > 0，必须保证StorageVolume是100的倍数。



## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUFileQuotaPrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUFileQuotaPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **StorageVolume** | int | 存储容量，单位: GB*天，范围: [0, 30 000 000]，步长：100GB*天 |No|
| **DownloadTraffic** | int | 下载流量，单位: GB，范围: [0, 60 000]，步长：1GB |No|
| **RequestCount** | int | 请求次数，单位：万次，范围：[0, 1 000 000]，步长：1万次 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 待支付价格，单位：分 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/uhost/?Action=GetUFileQuotaPrice
&Region=cn-bj2
&StorageVolume=200
&DownloadTraffic=5
&RequestCount=2
```

### 响应示例
    
```json
{
  "Action": "GetUFileQuotaPriceResponse",
  "Price": 346,
  "RetCode": 0
}
```





