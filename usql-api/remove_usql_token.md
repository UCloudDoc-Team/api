# 删除授权 - RemoveUSQLToken

## 简介

删除用户为USQL访问UCloud其他产品而申请的授权






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=RemoveUSQLToken)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RemoveUSQLToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|
| **DataSource** | string | 数据源类型， 如ufile |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Region** | string | 服务区域 |No|
| **DataSource** | string | 数据源类型， 如ufile |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RemoveUSQLToken
&Region=cn-bj
&DataSource=ufile
&ProjectId=cpzPYZle
```

### 响应示例
    
```json
{
  "Action": "RemoveUSQLTokenResponse",
  "DataSource": "ufile",
  "Region": "pre",
  "Request": "1a4c13be-e036-4e6d-9e75-7bc3df8349eb",
  "RetCode": 0
}
```





