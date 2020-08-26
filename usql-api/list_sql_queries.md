# 获取历史SQL查询列表 - ListSQLQueries

## 简介

获取用户提交过的历史SQL查询的列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListSQLQueries)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListSQLQueries`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|
| **Limit** | int | 查询个数（最大1000，默认100） |No|
| **Offset** | int | 偏移（默认0） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | API请求ID |No|
| **TotalCount** | int | 历史SQL查询总数 |No|
| **Queries** | array[[*QuerySummary*](#QuerySummary)] | SQL查询集合 |No|

#### 数据模型


#### QuerySummary

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **QueryId** | string | 查询ID |No|
| **QueryType** | string | 查询类型 |No|
| **QueryString** | string | 查询语句 |No|
| **State** | string | 查询状态 |No|
| **ScannedBytes** | int | 扫描字节数量 |No|
| **ErrorMessage** | string | 错误信息 |No|
| **ElapsedTimeMillis** | int | 查询耗时， 单位:：毫秒 |No|
| **StartTime** | int | 查询启动时间 |No|
| **EndTime** | int | 查询结束时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListSQLQueries
&Region=cn-bj
&ProjectId=apUufFKW
&Limit=2
&Offset=6
```

### 响应示例
    
```json
{
  "Action": "ListSQLQueriesResponse",
  "Queries": [
    {
      "EndTime": "2018-08-21T12:06:16.000+0000",
      "ErrorMessage": "line 1:16: Catalog hive-hadoop2 does not exist",
      "QueryId": "20180821_120614_00000_a2t8n",
      "ScannedBytes": 0,
      "StartTime": "2018-08-21T12:06:14.000+0000",
      "State": "FAILED"
    },
    {
      "EndTime": "2018-08-30T13:34:07.000+0000",
      "ErrorMessage": "line 1:15: Catalog hive-hadoop2 does not exist",
      "QueryId": "20180830_133406_00000_223ex",
      "ScannedBytes": 0,
      "StartTime": "2018-08-30T13:34:06.000+0000",
      "State": "FAILED"
    }
  ],
  "Request": "c1ce7672-ffa9-4d70-b35c-ba53d066f9ce",
  "RetCode": 0,
  "TotalCount": 124
}
```





