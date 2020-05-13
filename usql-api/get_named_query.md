# 获取命名SQL查询 - GetNamedQuery

## 简介

获取用户保存的SQL查询





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNamedQuery)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNamedQuery`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|
| **NamedQueryId** | int | 已命名查询的Id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | API请求ID |No|
| **QueryName** | string | SQL查询名称 |No|
| **QueryDescription** | string | SQL查询描述 |No|
| **QueryString** | string | SQL查询语句 |No|
| **CreateTime** | int | SQL查询保存时间 |No|
| **NamedQueryId** | int | SQL查询ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNamedQuery
&Region=pre
&NamedQueryId=1
&ProjectId=WiGGBLzY
```

### 响应示例
    
```json
{
  "Action": "GetNamedQueryResponse",
  "CreateTime": "2018-08-14T12:55:54.000+0000",
  "QueryDescription": "yyyyyyyyyy",
  "QueryId": 1,
  "QueryName": "named_sql",
  "QueryString": "SELECT * FROM xxxxxx;",
  "Request": "756275b6-b71c-4844-94b9-1f842b6d7a92",
  "RetCode": 0
}
```





