# 获取SQL查询详细信息 - GetSQLQuery

## 简介

获取用户提交的SQL查询任务的详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetSQLQuery)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSQLQuery`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|
| **QueryId** | string | SQL查询的ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | API请求ID |No|
| **QueryId** | string | SQL查询ID |No|
| **State** | string | 查询任务当前状态。<br />RUNNING： 正在运行，<br />CANCELLED：用户取消任务，<br />SUCCEED：任务运行成功，<br />FAILED： 任务运行失败 |No|
| **ElapsedTime** | int | 查询已运行时间 |No|
| **ScannedBytes** | int | 查询扫描数据字节数 |No|
| **QueryErrorCode** | int | 查询任务错误码 |No|
| **QueryErrorMessage** | string | 查询任务错误信息 |No|
| **StartTime** | int | 查询任务启动时间 |No|
| **EndTime** | int | 查询任务结束时间 |No|
| **Headers** | array[string] | 查询结果字段名列表 |No|
| **QueryType** | string | SQL查询类型， 有SELECT，CREATE_DATABASE, DROP_DATABASE, CREATE_TABLE, DROP_TABLE, SHOW_CREATE_TABLE |No|
| **OutputRecordCount** | int | 查询结果的记录总数 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSQLQuery
&Region=pre
&QueryId=20180913_082139_00000_22dwf
&ProjectId=iRdAMxGy
```

### 响应示例
    
```json
{
  "Action": "GetSQLQueryResponse",
  "ElapsedTime": 2363,
  "EndTime": "2018-09-13T08:21:42.000+0000",
  "Headers": [
    "n_nationkey",
    "n_name",
    "n_regionkey",
    "n_comment"
  ],
  "OutputRecordCount": 5,
  "QueryErrorCode": 0,
  "QueryErrorMessage": "",
  "QueryId": "20180913_082139_00000_22dwf",
  "QueryType": "fzWjVtIK",
  "Request": "dfa59d02-ae37-4386-80d4-686a3c3fa021",
  "RetCode": 0,
  "ScannedBytes": 2222,
  "StartTime": "2018-09-13T08:21:39.000+0000",
  "State": "SUCCEED"
}
```





