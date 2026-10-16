# 证书到期续费 - RenewCertificateOrder

## 简介

证书到期续费









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RenewCertificateOrder`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 待续费证书ID |**Yes**|
| **CertificateBrand** | string | 待续费证书品牌 |**Yes**|
| **CertificateName** | string | 待续费证书名称 |**Yes**|
| **DomainsCount** | int | 支持域名个数 |**Yes**|
| **ValidYear** | int | 有效期 |**Yes**|
| **CouponID** | string | 优惠券ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RenewCertificateOrder
&CertificateID=1
&CertificateBrand=TrustAsia
&CertificateName=TrustAsia-DV(1年)
&DomainsCount=1
&ValidYear=1
&CouponID=coupon-1234
```

### 响应示例
    
```json
{
  "Action": "RenewCertificateOrderResponse",
  "RetCode": 0
}
```





