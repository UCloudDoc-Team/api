# 获取证书对应的商品信息 - GetCertificateCommodity

## 简介

获取证书对应的商品信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCertificateCommodity`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 证书ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Commodity** | [*CertificateCommodity*](#CertificateCommodity) | 商品信息 |No|

#### 数据模型


#### CertificateCommodity

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | int | ID |No|
| **CertificateName** | string | 名称 |No|
| **CertificateBrand** | string | 品牌 |No|
| **CertificateCat** | string | 分类 |No|
| **ProductID** | int | 产品ID |No|
| **DomainMaxLimit** | int | 最大购买数量 |No|
| **DomainMinLimit** | int | 最小购买数量 |No|
| **Channel** | string | ca渠道 |No|
| **CertificateCnName** | string | 证书名 |No|
| **CSRAlgorithms** | array[[*CSRAlgorithmInfo*](#CSRAlgorithmInfo)] | 算法 |No|

#### CSRAlgorithmInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Algorithm** | string | 算法。<br /><br />支持RSA, ECDSA, SM2 三种值 |No|
| **AlgorithmOption** | array[string] | 算法key的长度 。 <br />1. RSA支持2048,3072,4096<br />2. ECDSA支持p256,p384,p512<br />3. SM2支持 p256 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCertificateCommodity
&CertificateID=tnTpaeWH
&Type=8
```

### 响应示例
    
```json
{
  "Action": "GetCertificateCommodityResponse",
  "Commodity": {},
  "RetCode": 0
}
```





