# 获取数据库中所有表 - ListCatalogTables

## 简介

获取用户指定的数据库中的所有表名称






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListCatalogTables)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListCatalogTables`                        | **Yes** |
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
| **Request** | string | 请求ID |No|
| **TotalCount** | int | 数据表总数 |No|
| **Tables** | array[[*Tables*](#Tables)] | 该数据库中数据表的集合 |No|

#### 数据模型


#### Tables

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Names** | string | 数据表名称 |**Yes**|
| **Columns** | array[[*Column*](#Column)] | 数据表的所有列 |**Yes**|

#### Column

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 列名称 |**Yes**|
| **Type** | string | 列的数据类型 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListCatalogTables
&Region=cn-bj
&Database=default
&ProjectId=oPcVYRZv
```

### 响应示例
    
```json
{
  "Action": "ListCatalogTablesResponse",
  "Request": "2bb5dd25-650b-4836-a7fa-0ca2e84ba2e8",
  "RetCode": 0,
  "Tables": [
    {
      "Columns": [
        {
          "Name": "n_nationkey",
          "Type": "bigint"
        },
        {
          "Name": "n_name",
          "Type": "string"
        },
        {
          "Name": "n_regionkey",
          "Type": "bigint"
        },
        {
          "Name": "n_comment",
          "Type": "string"
        }
      ],
      "Name": "nation"
    },
    {
      "Columns": [
        {
          "Name": "n_nationkey",
          "Type": "bigint"
        },
        {
          "Name": "n_name",
          "Type": "string"
        },
        {
          "Name": "n_regionkey",
          "Type": "bigint"
        },
        {
          "Name": "n_comment",
          "Type": "string"
        }
      ],
      "Name": "nation2"
    },
    {
      "Columns": [
        {
          "Name": "n_nationkey",
          "Type": "bigint"
        },
        {
          "Name": "n_name",
          "Type": "string"
        },
        {
          "Name": "n_regionkey",
          "Type": "bigint"
        },
        {
          "Name": "n_comment",
          "Type": "string"
        }
      ],
      "Name": "nation3"
    },
    {
      "Columns": [
        {
          "Name": "n_nationkey",
          "Type": "bigint"
        },
        {
          "Name": "n_name",
          "Type": "string"
        },
        {
          "Name": "n_regionkey",
          "Type": "bigint"
        },
        {
          "Name": "n_comment",
          "Type": "string"
        }
      ],
      "Name": "nation4"
    }
  ],
  "TotalCount": 4
}
```





