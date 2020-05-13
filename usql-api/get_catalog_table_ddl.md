# 获取数据表的DDL - GetCatalogTableDDL

## 简介

获取用户指定名称的数据表的创建DDL





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCatalogTableDDL)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCatalogTableDDL`                        | **Yes** |
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
| **TableDDL** | string | 数据表结构定义DDL |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCatalogTableDDL
&Region=xxx
&ProjectId=lCYjZaCF
&DatabaseName=default
&TableName=tbl4
```

### 响应示例
    
```json
{
  "Action": "GetCatalogTableDDLResponse",
  "DatabaseName": "default",
  "Request": "20d3da96-0edd-4429-ba5d-1c5901d6c88b",
  "RetCode": 0,
  "TableDDL": "CREATE EXTERNAL TABLE `tbl4`(\n`id` string)\nSTORED AS INPUTFORMAT\n'org.apache.hadoop.mapred.TextInputFormat'\nOUTPUTFORMAT\n'org.apache.hadoop.hive.ql.io.HiveIgnoreKeyTextOutputFormat'\nLOCATION\n'ufile://usql/tpc/tpch-s1/nation'\nTBLPROPERTIES (\n'skip.header.line.count'='1',\n'totalSize'='0',\n'delimiter'='|',\n'numFiles'='0',\n'transient_lastDdlTime'='1534840384',\n'classification'='csv')",
  "TableName": "tbl4"
}
```





