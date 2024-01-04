# 获取证书详情 - GetCertificateDetailInfo

## 简介

获取购买证书或托管证书的详情









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCertificateDetailInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 证书编号 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CertificateInfo** | [*CertificateInfo*](#CertificateInfo) | 证书信息 |**Yes**|
| **ApplicantInfo** | [*ApplicantInfo*](#ApplicantInfo) | 申请人信息，当为购买的证书才有此信息 |No|
| **CompanyInfo** | [*CompanyInfo*](#CompanyInfo) | 公司信息，当证书为购买时才有 |No|
| **OrderInfo** | array[[*OrderInfo*](#OrderInfo)] | 订单信息，当证书为购买时才有 |No|

#### 数据模型


#### CertificateInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 证书类型 |**Yes**|
| **CertificateID** | int | 证书id |**Yes**|
| **CertificateType** | string | 证书类型 |**Yes**|
| **CaOrganization** | string | 证书颁发机构 |**Yes**|
| **Algorithm** | string | 证书签名算法 |**Yes**|
| **ValidityPeriod** | int | 有限期几年 |**Yes**|
| **State** | string | 证书状态 |**Yes**|
| **StateCode** | string |  |**Yes**|
| **Name** | string | 证书名称 |**Yes**|
| **Brand** | string | 证书品牌 |**Yes**|
| **Domains** | string | 绑定域名 |**Yes**|
| **DomainsCount** | int | 域名数量 |**Yes**|
| **Mode** | string | 证书类型（购买，托管，免费）(purchase, trust, free) |**Yes**|
| **CSROnline** | int | 是否在线生成csr |**Yes**|
| **CSR** | string |  |**Yes**|
| **CSRKeyParameter** | string | 在线生成csr参数 |**Yes**|
| **CSREncryptAlgo** | string | 在线生成csr算法 |**Yes**|
| **IssuedDate** | int | 发布时间戳（秒） |**Yes**|
| **ExpiredDate** | int | 过期时间戳（秒） |**Yes**|

#### ApplicantInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 申请人姓名 |**Yes**|
| **Phone** | string | 申请人电话 |**Yes**|
| **Email** | string | 申请人邮箱 |**Yes**|

#### CompanyInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 公司名称 |**Yes**|
| **Division** | string | 部门 |**Yes**|
| **Phone** | string | 电话 |**Yes**|
| **Address** | string | 联系地址 |**Yes**|
| **City** | string | 省市 |**Yes**|
| **PostalCode** | string | 邮编 |**Yes**|

#### OrderInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceID** | string | 资源ID |**Yes**|
| **DomainsCount** | int | 域名个数 |**Yes**|
| **PurchaseTime** | int | 购买时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCertificateDetailInfo
&CertificateMode=purchase
&CertificateID=7
```

### 响应示例
    
```json
{
  "Action": "GetCertificateDetailInfoResponse",
  "ApplicantInfo": [
    "LrzNadXe",
    "BQJRVJxy",
    "ClffevkI",
    "ZwjaZITz",
    "oYagollE",
    "JIElzmgO"
  ],
  "CertificateInfo": [
    "TdmUzaEH",
    "zUQjWBQr",
    "NxjVlyUz",
    "iDFxLWwR",
    "agdrDiDq",
    "ULgIbciT",
    "OBrRuztS",
    "ztPyBlnr"
  ],
  "CompanyInfo": "WsUvPcYh",
  "OrderInfo": [
    "kbrFPjha",
    "fzakPjID",
    "AznNhMdG",
    "LQtKEHdw",
    "FjPEnuyL",
    "AcfKpFit",
    "eevTUVBD"
  ],
  "RetCode": 0
}
```





