# 获取域名解析记录 - UdnrDomainDNSQuery

## 简介

获取域名解析记录









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UdnrDomainDNSQuery`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Dn** | string | 域名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*DomainDNSRecord*](#DomainDNSRecord)] | 返回数据 |**Yes**|

#### 数据模型


#### DomainDNSRecord

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DnsType** | string | 解析记录类型 |No|
| **RecordName** | string | 解析记录名 |No|
| **Content** | string | 解析内容 |No|
| **Prio** | string | 优先级 |No|
| **TTL** | string | 生存时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UdnrDomainDNSQuery
&Dn=PCBCxdgw
```

### 响应示例
    
```json
{
  "Action": "UdnrDomainDNSQueryResponse",
  "Data": [
    "LABnjtBJ",
    "dzLcYkOQ",
    "PcoPMOHW",
    "nJhxDBFc",
    "dnbvwZxb",
    "jdsARdps",
    "sZKfalCe",
    "sMpNrQEx",
    "rTwLZVly"
  ],
  "Message": "YWMskZFN",
  "RetCode": 0
}
```





