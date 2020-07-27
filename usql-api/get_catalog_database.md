# 获取数据库 - GetCatalogDatabase

## 简介

获取数据目录下指定名称的数据库详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCatalogDatabase)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCatalogDatabase`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|
| **DatabaseName** | string | 数据库名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | API请求ID |No|
| **DatabaseName** | string | 数据库名称 |No|
| **DatabaseDescription** | string | 数据库描述 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCatalogDatabase
&Region=xxx
&ProjectId=klOgzUzQ
&DatabaseName=db_a

```

### 响应示例
    
```json
{
  "Action": "GetCatalogDatabaseResponse",
  "DatabaseDescription": "xxxxxxxxxxxx",
  "DatabaseName": "db_a",
  "Request": "a8aaf837-f969-4c98-adf9-22f20d7901f3",
  "RetCode": 0
}
```





