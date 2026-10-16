# 获取待确认的续费信息 - GetUnconfirmedComplementInfo

## 简介

获取待确认的续费信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUnconfirmedComplementInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 待确认续费信息的证书ID |**Yes**|
| **Type** | int | 请求类型，1-续费，2-重新颁发 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Details** | [*CSRInfo*](#CSRInfo) | CSRInfo |No|

#### 数据模型


#### CSRInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domains** | string | 证书绑定的域名，多个域名用逗号分隔，第一个域名为通用域名common name |**Yes**|
| **CSR** | string | 用户粘贴的CSR文件内容 |**Yes**|
| **CSROnline** | int | 在线生成证书 |**Yes**|
| **CSREncryptAlgo** | string | CSR加密算法 |**Yes**|
| **CSRKeyParameter** | string | 密钥对参数 |**Yes**|
| **CompanyName** | string | 公司名称 |**Yes**|
| **CompanyAddress** | string | 公司联系地址 |**Yes**|
| **CompanyRegion** | string | 公司所在省份 |**Yes**|
| **CompanyCity** | string | 公司所在城市 |**Yes**|
| **CompanyDivision** | string | 公司部门 |**Yes**|
| **CompanyCountry** | string | 国家码，默认为中国CN |**Yes**|
| **CompanyPhone** | string | 公司联系电话 |**Yes**|
| **CompanyPostalCode** | string | 公司邮编 |**Yes**|
| **CompanyType** | string | 公司类型 |**Yes**|
| **CompanyCodeType** | string | 公司代码类型 |**Yes**|
| **CompanyCode** | string | 公司代码 |**Yes**|
| **AdminName** | string | 申请人姓名 |**Yes**|
| **AdminPhone** | string | 申请人电话 |**Yes**|
| **AdminTitle** | string | 申请人职位 |**Yes**|
| **AdminEmail** | string | 申请人邮箱 |**Yes**|
| **DVAuthMethod** | string | DV证书的验证类型DNS\|FILE |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUnconfirmedComplementInfo
&CertificateID=21312312
&Type=1
```

### 响应示例
    
```json
{
  "Action": "GetUnconfirmedComplementInfoResponse",
  "Details": {
    "AdminEmail": "",
    "AdminName": "",
    "AdminPhone": "",
    "AdminTitle": "",
    "CSR": "",
    "CSREncryptAlgo": "",
    "CSRKeyParameter": "",
    "CSROnline": "",
    "CompanyAddress": "",
    "CompanyCity": "",
    "CompanyCode": "",
    "CompanyCodeType": "",
    "CompanyCountry": "",
    "CompanyDivision": "",
    "CompanyName": "",
    "CompanyPhone": "",
    "CompanyPostalCode": "",
    "CompanyRegion": "",
    "CompanyType": "",
    "DVAuthMethod": "",
    "Domains": "usecure_ussl"
  },
  "RetCode": 0
}
```





