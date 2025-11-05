# 购买证书 - PurchaseCertificate

## 简介

购买证书









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `PurchaseCertificate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateBrand** | string | 证书品牌 |**Yes**|
| **CertificateName** | string | 证书名称 |**Yes**|
| **DomainsCount** | int | 域名个数 |**Yes**|
| **ValidYear** | string | 证书有效期，单位是年 |**Yes**|
| **CouponID** | string | 优惠券ID |No|
| **ActivityID** | int | 活动ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CertificateID** | int | 购买的证书ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=PurchaseCertificate
&CertificateBrand=TrustAsia
&CertificateName=TrustAsiaDVG5
&DomainsCount=1
&ValidYear=3
&CouponID=ifyouhavecoupon
&ActivityID=ifyouhaveactivity
```

### 响应示例
    
```json
{
  "Action": "PurchaseCertificateResponse",
  "CertificateID": 5234233,
  "RetCode": 0
}
```





