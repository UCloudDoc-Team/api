# 删除解析记录 - UdnrDeleteDnsRecord

## 简介

删除解析记录









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UdnrDeleteDnsRecord`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Dn** | string | 域名 |**Yes**|
| **RecordName** | string | 记录名 |**Yes**|
| **DnsType** | string | 记录类型 |**Yes**|
| **Content** | string | 解析内容 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | object | 返回数据 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UdnrDeleteDnsRecord
&Dn=FwpOsAiM
&RecordName=QwCphQJv
&DnsType=daMyiiQT
&Content=VMTgcDHO
```

### 响应示例
    
```json
{
  "Action": "UdnrDeleteDnsRecordResponse",
  "Data": {},
  "Message": "EygAdLFr",
  "RetCode": 0
}
```





