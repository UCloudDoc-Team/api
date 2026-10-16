# 获取用户证书列表 - GetCertificateList

## 简介

获取用户证书列表，包括购买证书和托管证书









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCertificateList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Mode** | string | purchase-购买, trust-托管, free-免费 |**Yes**|
| **StateCode** | string | 状态码 |No|
| **Brand** | string | 品牌 |No|
| **Domain** | string | 模糊匹配域名 |No|
| **Sort** | string | 1-升序，2-降序 |No|
| **Page** | int | 页码 |No|
| **PageSize** | int | 每页数量 |No|
| **CaOrganization** | string | 证书供应商 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 证书的总个数 |**Yes**|
| **CertificateList** | array[[*CertificateList*](#CertificateList)] | 证书列表 |**Yes**|

#### 数据模型


#### CertificateList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 证书Id |**Yes**|
| **CertificateSN** | string | 证书资源ID |**Yes**|
| **CertificateCat** | string | 证书分类 |**Yes**|
| **Mode** | string | 证书类型 |**Yes**|
| **Domains** | string | 证书绑定域名 |**Yes**|
| **Brand** | string | 证书所属品牌商 |**Yes**|
| **ValidityPeriod** | int | 域名有效年限 |**Yes**|
| **Type** | string | 证书颁发机构信息 |**Yes**|
| **NotBefore** | int | 颁发日期(毫秒时间戳) |**Yes**|
| **NotAfter** | int | 过期日期(毫秒时间戳） |**Yes**|
| **AlarmState** | int | 是否过期告警 |**Yes**|
| **StateCode** | string | 证书状态码 |**Yes**|
| **State** | string | 证书状态说明 |**Yes**|
| **Name** | string | 证书名称英文 |**Yes**|
| **MaxDomainsCount** | int | 最大域名数量 |**Yes**|
| **DomainsCount** | int | 当前域名数量 |**Yes**|
| **CaChannel** | string | 第三方证书机构 |**Yes**|
| **CSRAlgorithms** | array[[*CSRAlgorithmInfo*](#CSRAlgorithmInfo)] | csr可选加密信息 |**Yes**|
| **TopOrganizationID** | int | 公司ID |**Yes**|
| **OrganizationID** | int | 项目ID |**Yes**|
| **IsFree** | int | 是否免费 |**Yes**|
| **YearOfValidity** | int | 新增多年期第几年 |**Yes**|
| **Channel** | int | 渠道信息 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **CertificateUrl** | string | 证书下载的url |**Yes**|

#### CSRAlgorithmInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Algorithm** | string | 算法。<br /><br />支持RSA, ECDSA, SM2 三种值 |No|
| **AlgorithmOption** | array[string] | 算法key的长度 。 <br />1. RSA支持2048,3072,4096<br />2. ECDSA支持p256,p384,p512<br />3. SM2支持 p256 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCertificateList
&Mode=dtohZPCB
&StateCode=yuZLjUmi
&Brand=slEEjSqt
&Domain=mFfakwWg
&Sort=mVcVDzaF
&Limit=1
&Offset=5
&CaOrganization=LrPWfhEg
&Channel=2
```

### 响应示例
    
```json
{
  "Action": "GetCertificateListResponse",
  "CertificateList": [
    {
      "Domains": "www.bestenover.com",
      "Expire": 1515455999,
      "ID": 1,
      "Mode": "purchase",
      "Name": "TestCSROnlineFreeSSL",
      "State": "订单完成",
      "Type": "Synamtic-亚洲诚信(1年)"
    },
    {
      "Domains": "bestenover.com",
      "Expire": 1544918399,
      "ID": 6,
      "Mode": "trust",
      "Name": "TestTrustedCertificate",
      "State": "托管中",
      "Type": "COMODO CA Limited-PositiveSSL(3年)"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





