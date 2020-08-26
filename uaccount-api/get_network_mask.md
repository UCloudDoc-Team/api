# 查询登录与API调用的网络掩码 - GetNetworkMask

## 简介

查询登录与API调用的网络掩码






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNetworkMask)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNetworkMask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*NetworkMask*](#NetworkMask) | 接口返回数据 |No|

#### 数据模型


#### NetworkMask

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **APINetworkMask** | string | API调用网络掩码，默认空字符串，不限制登录IP，多个IP以英文逗号分隔。 |**Yes**|
| **LoginNetworkMask** | string | 登录网络掩码，默认空字符串，不限制登录IP，多个IP以英文逗号分隔。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNetworkMask
```

### 响应示例
    
```json
{
  "Data": {},
  "Message": "success",
  "NetworkMask": {},
  "RetCode": 0
}
```





