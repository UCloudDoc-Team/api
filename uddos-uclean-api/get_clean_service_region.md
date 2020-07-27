# 获取可用地域 - GetCleanServiceRegion

## 简介

获取可用地域






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCleanServiceRegion)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCleanServiceRegion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Area** | string | [境内：domestic 境外：oversea 全部：all],默认all |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CleanRegion** | array[string] | 通过GetCleanServiceRegion 维护更新可用的地域列表以应对日益扩张的机房。截止至2019-01-24现网目前可用的列表如下：LosAngeles,Washington,Frankfurt,Singapore,Kaohsiung,Moscow,Tokyo,Taipei |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCleanServiceRegion
&Area=[境内：domestic境外：oversea全部：all]
```

### 响应示例
    
```json
{
  "Action": "GetCleanServiceRegionResponse",
  "Region": [
    "WNGYrBNW",
    "ZjHmQKBk",
    "BhsHKcGG",
    "cYzABwdM",
    "ArDRHDPs",
    "OiAFIHNa",
    "tMjFswFY",
    "YFjoMQOL",
    "NDcVohPo",
    "tDXfVkhC"
  ],
  "RetCode": 0
}
```





