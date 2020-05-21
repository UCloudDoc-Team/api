# 获取waf防护域名列表 - DescribeWafDomainHostInfo

## 简介

获取waf防护域名列表








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafDomainHostInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Limit** | int | 每页数量限制(等效page size) |**Yes**|
| **Offset** | int | 页面偏移(等效page number) |**Yes**|
| **FullDomain** | string | 域名，用于查询单一域名 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | string | 域名总数 |No|
| **DomainHostList** | array[[*HostStatausInfo*](#HostStatausInfo)] | 域名信息列表，参考HostStatausInfo |No|

#### 数据模型


#### HostStatausInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **FullDomain** | string | 域名 |No|
| **WorkMode** | string | 工作模式 |No|
| **RecordID** | int | 域名记录ID |No|
| **CertificateID** | int | 证书ID |No|
| **Cname** | string | CNAME记录值 |No|
| **WorkRegions** | string | 部署区域 |No|
| **AntiCC** | string | 是否开启CC防护 |No|
| **Assurance** | string | 是否开启网页防篡改 |No|
| **CreateTime** | int | 创建时间戳 |No|
| **SrcIPInfo** | array[[*SrcIPInfo*](#SrcIPInfo)] | 源站IP地址信息，参考SrcIPInfo |No|
| **HTTPRedirection** | string | http是否重定向 |No|
| **HTTPStatus** | string | http状态描述 |No|
| **HTTPException** | string | http异常信息 |No|
| **HTTPSStatus** | string | https状态 |No|
| **HTTPSException** | string | https异常描述 |No|
| **UniqueIP** | string | 是否独享IP地址 |No|
| **RealIPHeader** | string | 真实IP头部 |No|
| **AttackCount** | int | 攻击次数 |No|
| **DomainStatus** | array[[*DomainStatus*](#DomainStatus)] | 域名状态信息，参考DomainStatus |No|
| **DefenceIps** | object | 防御IP地址表(map)，如：{"cn-gd":["192.168.1.2","192.168.1.3"] |No|

#### SrcIPInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Proto** | string | 协议 |No|
| **Ip** | string | 源IP地址 |No|
| **Ports** | array[int] | 源端口 |No|
| **URI** | string | URI |No|

#### DomainStatus

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 部署区域 |No|
| **Scheme** | string | 协议 |No|
| **Status** | string | 状态信息 |No|
| **RawStatus** | string | 原始状态信息 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafDomainHostInfo
&ProjectId=org-xxx
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "DescribeWafDomainHostInfoResponse",
  "DomainHostList": [
    {
      "AntiCC": "on",
      "Assurance": "off",
      "AttackCount": 0,
      "CertificateID": 0,
      "Cname": "ce43b831.uewaf.com",
      "CreateTime": 1584695681,
      "DefenceIps": {
        "cn-bj": [
          "106.7.27.194"
        ],
        "cn-gd": [
          "106.7.185.203"
        ]
      },
      "DomainStatus": [
        {
          "RawStatus": "Head http://106.5.185.203:80/: EOF",
          "Region": "cn-gd",
          "Scheme": "http",
          "Status": "Exception"
        },
        {
          "RawStatus": "Head http://106.5.27.194:80/: EOF",
          "Region": "cn-bj",
          "Scheme": "http",
          "Status": "Exception"
        }
      ],
      "FullDomain": "www.test.com",
      "HTTPRedirection": "NO",
      "HttpException": "Head http://106.5.27.194:80/: EOF",
      "HttpStatus": "Exception",
      "HttpsException": "",
      "HttpsStatus": "Unaccess",
      "RealIPHeader": "default",
      "RecordId": 46103,
      "SrcIPInfo": [
        {
          "Port": [
            80
          ],
          "Proto": "http",
          "SrcIP": "152.32.70.130",
          "URI": "http://152.32.170.130:80"
        }
      ],
      "UniqueIP": "NO",
      "WorkMode": "Alarm",
      "WorkRegions": "cn-bj,cn-gd"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





