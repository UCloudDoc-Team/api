# 查询证书告警列表 - GetAlarmCertificateList

## 简介

查询证书告警列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAlarmCertificateList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **AlarmType** | int | 告警类型，不填默认查询所有，1:加入告警，0:未加入告警<br />默认填充为1 |No|
| **Sort** | string | 1-升序，2-降序 |No|
| **Limit** | int | 返回数据长度，默认为20 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 记录总数 |No|
| **CertificateList** | array[[*CertificateList*](#CertificateList)] | 返回符合条件的证书记录列表 |No|

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
https://api.ucloud.cn/?Action=GetAlarmCertificateList
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=CYpfcAIF
&AlarmType=1
```

### 响应示例
    
```json
{
  "Action": "GetAlarmCertificateListResponse",
  "CertificateList": [
    {
      "AlarmState": 1,
      "Brand": "TrustAsia",
      "CSRAlgorithms": [
        {
          "Algorithm": "RSA",
          "AlgorithmOption": [
            "2048"
          ]
        }
      ],
      "CaChannel": "TrustAsia",
      "CertificateCat": "DV",
      "CertificateID": 1,
      "CertificateSN": "usecure_ussl-2",
      "CertificateUrl": "https://ussl.cn-bj.ufileos.com/usecure_ussl-2",
      "Channel": 1,
      "CreateTime": 1671421768,
      "Domains": "test1.com",
      "DomainsCount": 1,
      "ID": 1,
      "IsFree": 1,
      "MaxDomainsCount": 1,
      "Mode": "free",
      "Name": "TrustAsiaDVG5",
      "NotAfter": 1706745599000,
      "NotBefore": 1675123200000,
      "OrganizationID": 2,
      "State": "待续费",
      "StateCode": "WF_RENEW",
      "TopOrganizationID": 2,
      "Type": "TrustAsia-DV(1年)",
      "ValidityPeriod": 1,
      "YearOfValidity": 1
    },
    {
      "AlarmState": 1,
      "Brand": "TrustAsia Technologies, Inc.",
      "CSRAlgorithms": null,
      "CaChannel": "",
      "CertificateCat": "",
      "CertificateID": 2,
      "CertificateSN": "usecure_ussl-3",
      "CertificateUrl": "https://ussl.cn-bj.ufileos.com/usecure_ussl-3",
      "Channel": 1,
      "CreateTime": 1658473462,
      "Domains": "test2.com",
      "DomainsCount": 1,
      "ID": 2,
      "IsFree": 0,
      "MaxDomainsCount": 0,
      "Mode": "trust",
      "Name": "test",
      "NotAfter": 1686095999000,
      "NotBefore": 1654560000000,
      "OrganizationID": 2,
      "State": "托管中",
      "StateCode": "TRUSTING",
      "TopOrganizationID": 2,
      "Type": "TrustAsia Technologies, Inc.(1年)",
      "ValidityPeriod": 1,
      "YearOfValidity": 0
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





