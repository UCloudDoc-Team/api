# 创建短链接 - CreateUSLKShortLink

## 简介

创建短链接









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUSLKShortLink`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LongLinkID** | int | 长链接ID，状态必须为审核通过 |**Yes**|
| **StartTime** | int | 开始生效时间戳, 传 3376656000 表示生成永久生效短链接 |**Yes**|
| **EndTime** | int | 过期时间戳，传 3376656000 表示生成永久生效短链接 |**Yes**|
| **Type** | int | 链接类型-预留：普通跳转、随机跳转，当前默认普通跳转 1: 普通跳转 |**Yes**|
| **Proto** | string | 协议名称：http/https |**Yes**|
| **ShortLinkDomain** | string | 短链接域名，默认：uslk.net |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ShortLink** | string | 生成的短链接内容 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUSLKShortLink
&LongLinkID=4
&StartTime=9
&EndTime=7
&Type=9
&Proto=NRzAobRq
&ShortLinkDomain=NxiXMBxY
```

### 响应示例
    
```json
{
  "Action": "CreateUSLKShortLinkResponse",
  "Message": "PeuIxect",
  "RetCode": 0,
  "ShortLink": "TNwjuevK"
}
```





