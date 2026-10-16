# 补全CSR的信息 - ComplementCSRInfo

## 简介

补全CSR的信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ComplementCSRInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 购买证书的编号 |**Yes**|
| **Domains** | string | 证书绑定的域名，多个域名用逗号分隔，第一个域名为通用域名cnname |**Yes**|
| **CSROnline** | int | 是否在线生成csr,  0-复制，1-在线生成 |**Yes**|
| **CompanyName** | string | 公司名称 |**Yes**|
| **CompanyAddress** | string | 公司联系地址 |**Yes**|
| **CompanyRegion** | string | 所在省份 |**Yes**|
| **CompanyCity** | string | 所在城市 |**Yes**|
| **CompanyCountry** | string | 国家码，默认为中国CN |**Yes**|
| **CompanyDivision** | string | 公司部门 |**Yes**|
| **AdminName** | string | 申请人姓名 |**Yes**|
| **AdminPhone** | string | 申请人电话 |**Yes**|
| **AdminEmail** | string | 申请人邮箱 |**Yes**|
| **AdminTitle** | string | 申请人职位 |**Yes**|
| **DVAuthMethod** | string | DV证书验证类型 |**Yes**|
| **CompanyPhone** | string | 公司联系电话 |No|
| **CompanyPostalCode** | string | 公司邮编 |No|
| **CompanyType** | string | 机构类型 |No|
| **CompanyCodeType** | string | 机构码类型 |No|
| **CompanyCode** | string | 机构码 |No|
| **CSR** | string | 复制的csr   （CSROnline为0时必填） |No|
| **CSREncryptAlgo** | string | CSR加密算法     （CSROnline为1时必填） |No|
| **CSRKeyParameter** | string | 密钥对参数   （CSROnline为1时必填） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ComplementCSRInfo
&CertificateID=8
&CertificateName=SecureSiteProEV
&ValidityPeriod=2
&CsrEncryptAlgo=ECDSA
&Domains=PeJsuDRD
&CsrKeyParameter=prime256v1
&OrganizationName=DUThgCax
&AddressLine=POhfmibL
&OrgRegion=OOKnBtlT
&City=OnTwomyx
&Country=uylWlIZi
&OrgPhone=JwOiDiJH
&PostalCode=FSfpwLoa
&AdminName=RiQBMoxy
&AdminPhone=NOLTPRuX
&AdminEmail=QLnKUWIl
&AdminTitle=cgnxcmPX
&Division=QqbNMIkT
&DVAuthMethod=DNS
&NewProperty=XJqFOYWs
&CompanyType=tDRakRYj
&CompanyCodeType=JbPNyrmA
&CompanyCode=XhnPAjzK
&AdminFirstName=zVCdeJUB
&AdminLastName=skDfHQtt
&AdminFirstName=VmNakDAe
&AdminLastName=LYWLvnsE
```

### 响应示例
    
```json
{
  "Action": "ComplementCSRInfoResponse",
  "ApplyTime": 5,
  "AuthMethod": "DNS",
  "Auths": [
    {
      "AppName": "aBnsVqxQ"
    }
  ],
  "CN": "IiLtCrBm",
  "CertificateState": "HYNPXWjV",
  "RetCode": 0
}
```





