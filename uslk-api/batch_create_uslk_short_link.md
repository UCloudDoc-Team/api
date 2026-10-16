# 批量创建短链接【免审】 - BatchCreateUSLKShortLink

## 简介

批量创建短链接【免审】









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BatchCreateUSLKShortLink`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ScenarioID** | int | 场景ID |**Yes**|
| **LongLinks.N** | string | 长链接数组，示例: "LongLinks.0": "http://ucloud.cn/0", "LongLinks.1": "http://ucloud.cn/1" |**Yes**|
| **StartTime** | int | 开始生效时间戳（秒级）, 传 3376656000 表示生成永久生效短链接 |**Yes**|
| **EndTime** | int | 过期时间戳（秒级），传 3376656000 表示生成永久生效短链接 |**Yes**|
| **Proto** | string | 协议名称：http/https |**Yes**|
| **ShortLinkDomain** | string | 短链接域名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ShortLinks** | array[string] | 创建成功的短链接，根据传LongLinks顺序排列 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BatchCreateUSLKShortLink
&LongLinks.N=http://baidu.com
&StartTime=3376656000
&EndTime=3376656000
&Proto=http
&ShortLinkDomain=uslk.net
&ScenarioID=9
```

### 响应示例
    
```json
{
  "Action": "BatchCreateUSLKShortLinkResponse",
  "Message": "LDXldvib",
  "RetCode": 0,
  "ShortLinks": [
    "http://me1.ltd/lmpne5t"
  ]
}
```





