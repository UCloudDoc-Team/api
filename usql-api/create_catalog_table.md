# 创建表 - CreateCatalogTable

## 简介

在数据目录中的指定数据库下创建新的数据表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateCatalogTable)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCatalogTable`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|
| **DatabaseName** | string | 数据库的名称 |**Yes**|
| **TableName** | string | 数据表的名称 |**Yes**|
| **Location** | string | 数据存储位置，如：ufile://usql/tpc/tpch-s1/nxxxx |**Yes**|
| **Column.N.Name** | string | 第N个字段的名称，例如：第一个字段的名称：Column.0.Name |**Yes**|
| **Column.N.Type** | string | 第N个字段的类型，例如：第一个字段的类型：Column.0.Type |**Yes**|
| **Formation** | string | 数据格式：比如CSV，ORC， TSV等 |**Yes**|
| **Property.N.Key** | string | 第N个表属性的值，例如：第一个表属性的名称：Property.0.Key |No|
| **Property.N.Value** | string | 第N个表属性的值，例如：第一个表属性的值：Property.0.Value |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | API请求的ID |No|
| **DatabaseName** | string | 新数据表所属数据库名称 |No|
| **TableName** | string | 新数据表的名称 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCatalogTable
&Region=cn-zj
&ProjectId=JQswhxDD
&DatabaseName=db_a
&TableName=nation
&Location=ufile://usql/tpc/tpch-s1/nation
&Formation=CSV
&Column.0.Name=n_nationkey
&Column.0.Type=bigint
&Column.1.Name=n_name
&Column.1.Type=string
&Column.2.Name=n_regionkey
&Column.2.Type=bigint
&Column.3.Name=n_comment
&Column.3.Type=string
&Property.0.Key=delimiter
&Property.0.Value=,
&Property.1.Name=classification
&Property.1.Type=csv
&Property.2.Name=skip.header.line.count
&Property.2.Type=1
```

### 响应示例
    
```json
{
  "Action": "CreateCatalogTableResponse",
  "DatabaseName": "db_a",
  "Request": "1c5acb36-e5b4-46af-b9b1-52455cd53175",
  "RetCode": 0,
  "TableName": "nation"
}
```





