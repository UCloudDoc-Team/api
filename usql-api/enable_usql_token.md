# 设置USQL授权的状态 - EnableUSQLToken

## 简介

用户可以开启/关闭其他产品为USQL开通的授权






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=EnableUSQLToken)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `EnableUSQLToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID， 不填则为默认项目 |No|
| **DataSource** | string | 数据源类型，如ufile |**Yes**|
| **State** | int | 0: 关闭， 1: 开启 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | API请求ID |No|
| **DataSourceType** | string | 数据源名称， 如ufile |No|
| **Enable** | boolean | true： 该授权已经启用<br />false: 该授权已经关闭 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=EnableUSQLToken
&Region=xxx
&ProjectId=mDwzQJik
&DataSourceType=ufile
&State=1
&DataSource=UxRYTgTY
```

### 响应示例
    
```json
{
  "Action": "EnableUSQLTokenResponse",
  "DataSourceType": "ufile",
  "Enable": true,
  "Request": "177fcc1e-19ae-403c-9832-c1f970b28877",
  "RetCode": 0
}
```





