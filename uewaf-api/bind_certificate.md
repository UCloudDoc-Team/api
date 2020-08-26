# 绑定SSL证书 - BindCertificate

## 简介

绑定新的SSL证书到指定域名









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BindCertificate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **CertificateID** | int | SSL证书ID，可通过DescribeWafDomainCertificateInfo查询 |**Yes**|
| **FullDomain** | string | 需要绑定证书的域名，必须与证书同属一个一级域名 |**Yes**|
| **CertificateName** | string | 证书名称 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BindCertificate
&ProjectId=org-xxx
&CertificateID=901
&FullDomain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "BindCertificateResponse",
  "RetCode": 0
}
```





