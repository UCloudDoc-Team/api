# 获取证书 - GetCertificateV2

## 简介

获取证书列表(新)






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCertificateV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCertificateV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CdnDomain** | string | 根据加速域名筛选对应的证书 |No|
| **Offset** | int | 偏移，默认为0，非负整数 |No|
| **Limit** | int | 长度，默认为全部，非负整数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 证书数量 |**Yes**|
| **CertList** | array[[*CertList*](#CertList)] | 证书信息列表 |**Yes**|

#### 数据模型


#### CertList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertName** | string | 证书名 |**Yes**|
| **CommonName** | string | 通用名 |**Yes**|
| **DnsName** | string | dns名称 |**Yes**|
| **BeginTime** | int | 证书开始时间 |**Yes**|
| **EndTime** | int | 证书获取时间 |**Yes**|
| **DomainCount** | int | 已配置域名个数 |**Yes**|
| **UserCert** | string | 证书内容 |**Yes**|
| **CaCert** | string | ca证内容 |**Yes**|
| **Domains** | array[string] | 已配置的域名列表 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCertificateV2
&ProjectId=GfZloUyO
&Offset=8
&Limit=6
&CdnDomain=oKNiSllO
```

### 响应示例
    
```json
{
  "Action": "GetCertificateV2Response",
  "CertList": [
    {
      "BeginTime": 6,
      "CaCert": "dbvZSNyE",
      "CertName": "tGFFxvhj",
      "CommonName": "EfockrQK",
      "DnsName": "xjhMPWqV",
      "DomainCount": 8,
      "EndTime": 4,
      "UserCert": "rEAUBqQv"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





