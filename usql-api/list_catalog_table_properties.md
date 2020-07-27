# 获取数据表的参数列表 - ListCatalogTableProperties

## 简介

获取用户指定名称的数据表的所有参数






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListCatalogTableProperties)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListCatalogTableProperties`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|
| **DatabaseName** | string | 数据库名称 |**Yes**|
| **TableName** | string | 数据表名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | API请求ID |No|
| **DatabaseName** | string | 数据库名称 |No|
| **TableName** | string | 数据表名称 |No|
| **TableProperties** | array[[*TableProperty*](#TableProperty)] | 数据表属性列表 |No|

#### 数据模型


#### TableProperty

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Value** | string | 属性值 |No|
| **Name** | string | 属性名 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListCatalogTableProperties
&Region=cn-xxx
&ProjectId=ilbjABtv
&DatabaseName=default
&TableName=tbl3


```

### 响应示例
    
```json
{
  "Action": "ListCatalogTablePropertiesResponse",
  "DatabaseName": "default",
  "Request": "81b7b1b3-2a61-4d68-8124-622a982c5c3f",
  "RetCode": 0,
  "TableName": "tbl3",
  "TableProperties": [
    {
      "Name": "skip.header.line.count",
      "Value": "1"
    },
    {
      "Name": "totalSize",
      "Value": "0"
    },
    {
      "Name": "delimiter",
      "Value": "|"
    },
    {
      "Name": "numFiles",
      "Value": "0"
    },
    {
      "Name": "transient_lastDdlTime",
      "Value": "1534822799"
    },
    {
      "Name": "classification",
      "Value": "csv"
    }
  ]
}
```





