# 增加授权 - AddUSQLToken

## 简介

为USQL增加访问其他UCloud产品的授权Token






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddUSQLToken)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUSQLToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 用户项目ID， 用户不填则为默认项目 |No|
| **DataSource** | string | 数据源类型， 如ufile |**Yes**|
| **AccessKeyId** | string | 令牌密钥对中的公钥 |**Yes**|
| **AccessKeySecret** | string | 令牌密钥对中的私钥 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Region** | string | 服务区域 |No|
| **DataSource** | string | 令牌对应的数据源名称， 如ufile |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUSQLToken
&Region=cn-bj2
&ProjectId=SgZsaQGG
&DataSourceType=ufile
&AccessKeyId=xxxxx
&AccessKeySecret=yyyyy

```

### 响应示例
    
```json
{
  "Action": "AddUSQLTokenResponse",
  "DataSource": "ufile",
  "Region": "xxx",
  "RetCode": 0
}
```





