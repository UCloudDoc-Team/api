# 报备长链接 - CreateUSLKLongLink

## 简介

报备长链接









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUSLKLongLink`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ScenarioID** | int | 场景ID |**Yes**|
| **LongLink** | string | 要报备的长链接 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ReqUuid** | string | ReqUuid |No|
| **LongLinkID** | int | 长链接ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUSLKLongLink
&ScenarioID=cVAXqmKg
&LongLink=FYSJhDXw
```

### 响应示例
    
```json
{
  "Action": "CreateUSLKLongLinkResponse",
  "LongLinkID": 4,
  "Message": "nbysUcSF",
  "ReqUuid": "KXlIqQae",
  "RetCode": 0
}
```





