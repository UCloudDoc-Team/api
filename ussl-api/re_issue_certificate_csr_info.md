# 重新颁发补充CSR证书 - ReIssueCertificateCSRInfo

## 简介

重新颁发补充CSR证书









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ReIssueCertificateCSRInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 证书编号 |**Yes**|
| **CSROnline** | string | csr来源 0-本地粘贴，1-在线生成 |**Yes**|
| **CSR** | string | csr  CSROnline=0时必填 |No|
| **CSREncryptAlgo** | string | 加密算法 CSROnline=1时必填<br />支持RSA, ECDSA, SM2 三种值 |No|
| **CSRKeyParameter** | string | 加密算法的参数  CSROnline=1时必填<br />1. RSA支持2048,3072,4096 <br />2. ECDSA支持p256,p384,p512 <br />3. SM2支持 p256 |No|
| **Domains** | string | 域名，多个域名使用逗号分隔 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ReIssueCertificateCSRInfo
&CertificateID=2
&CsrEncryptAlgo=ECDSA
&CsrKeyParameter=p256
&Domains=www.test1.com
&CSROnline=0
&CSR=a1b2c3d4f5a2b3c4d5f6
```

### 响应示例
    
```json
{
  "Action": "ReIssueCertificateCSRInfoResponse",
  "RetCode": 0
}
```





