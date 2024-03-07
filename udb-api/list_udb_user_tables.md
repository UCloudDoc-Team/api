# 查看udb实例的用户表集合 - ListUDBUserTables

## 简介

查看udb实例所有的用户表集合 （只包括引擎为innodb和myisam的表）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUDBUserTables)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUDBUserTables`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **DBId** | string | udb实例的ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Tables** | array[[*UDBDatabaseData*](#UDBDatabaseData)] | 用户库表的集合 |**Yes**|

#### 数据模型


#### UDBDatabaseData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DBName** | string | 数据库名称 |**Yes**|
| **TableDataSet** | array[[*TableData*](#TableData)] | 该库所有的表集合 |**Yes**|

#### TableData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TableName** | string | 表名称 |**Yes**|
| **DBName** | string | 表所属的库名称 |**Yes**|
| **Engine** | string | 表的引擎（innodb, myisam） |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUDBUserTables
&Region=cn-zj
&DBId=VqOTzPFh
```

### 响应示例
    
```json
{
  "Action": "ListUDBUserTablesResponse",
  "RetCode": 0,
  "Tables": [
    {
      "DBName": "wqrPZnjX",
      "TableDataSet": [
        {
          "DBName": "pkuKFgfr",
          "Engine": "QKYqWolU",
          "TableName": "xHNesJxX"
        }
      ]
    }
  ]
}
```





