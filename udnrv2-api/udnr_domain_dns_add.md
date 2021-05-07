# 添加解析记录 - UdnrDomainDNSAdd

## 简介

添加解析记录









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UdnrDomainDNSAdd`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Dn** | string | 域名 |**Yes**|
| **RecordName** | string | 解析记录名 |**Yes**|
| **DnsType** | string | 记录类型 |**Yes**|
| **Content** | string | 解析内容 |**Yes**|
| **TTL** | string | 生存时间 |**Yes**|
| **Prio** | string | 优先级 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | string | 返回数据 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UdnrDomainDNSAdd
&Dn=lNTBtwAP
&RecordName=ksBoPemB
&DnsType=wYiwMUPL
&Content=FRVfOnci
&TTL=SjdoyeBq
&Prio=PhDLVHOD
```

### 响应示例
    
```json
{
  "Action": "UdnrDomainDNSAddResponse",
  "Data": "BFtLtuKv",
  "Message": "CardVtDd",
  "RetCode": 0
}
```





