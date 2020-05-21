# 显示域名对应的证书 - DescribeWafDomainCertificateInfo

## 简介

显示域名对于的证书








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafDomainCertificateInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Domain** | string | 要查询域名，为空时查找所有 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 证书数量 |No|
| **CertificateInfo** | [*DoaminCertificateInfo*](#DoaminCertificateInfo) | 证书详情列表，参考DoaminCertificateInfo |No|

#### 数据模型


#### DoaminCertificateInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 证书ID |No|
| **CertificateName** | string | 证书名称 |No|
| **Domain** | string | 证书一级域名 |No|
| **UploadTime** | object | 证书入库时间，utc时间格式，如：2020-02-06T18:46:17+08:00 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafDomainCertificateInfo
&ProjectId=org-xxx
&Domain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "DescribeWafDomainCertificateInfoResponse",
  "CertificateInfo": [
    {
      "CertificateID": 834,
      "CertificateName": "test",
      "Domain": "test.com",
      "UploadTime": "2020-02-06T18:46:17+08:00"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





