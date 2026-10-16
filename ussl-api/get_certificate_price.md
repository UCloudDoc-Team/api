# 获取证书价格 - GetCertificatePrice

## 简介

获取证书价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCertificatePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateBrand** | string | 证书品牌 |**Yes**|
| **CertificateName** | string | 证书名称 |**Yes**|
| **DomainsCount** | int | 域名个数 |**Yes**|
| **ValidYear** | int | 证书有效期，年限 |**Yes**|
| **ActivityID** | int | 活动id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 证书价格 |**Yes**|
| **OriginalPrice** | float | 原价 |No|
| **FreeQuota** | int | 免费证书个数 |No|
| **Available** | int | 免费证书可用 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCertificatePrice
```

### 响应示例
    
```json
{
  "Action": "GetCertificatePriceResponse",
  "Available": 4,
  "FreeQuota": 2,
  "OriginalPrice": 8.76199,
  "RetCode": 0
}
```





