# 列出MySQL 慢日志明细 - ListUDACMySQLSlowLog

## 简介

列出MySQL 慢日志明细






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUDACMySQLSlowLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUDACMySQLSlowLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **InstanceID** | string | 数据库实例ID |**Yes**|
| **StartTime** | int | 开始时间，unix时间戳 |**Yes**|
| **EndTime** | int | 结束时间，unix时间戳 |**Yes**|
| **Offset** | int | 页数，从1开始 |**Yes**|
| **Limit** | int | 每页条目数量 |**Yes**|
| **Database** | string | 库名 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | StartTime到EndTime时间范围内的数据总条目数 |**Yes**|
| **SlowLogDataSet** | array[[*SlowLogData*](#SlowLogData)] | 慢日志数据 |**Yes**|
| **MaxDownloadCount** | int | 慢日志数据下载数上限 |No|

#### 数据模型


#### SlowLogData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ExecutedTime** | int | 执行完成时间 |No|
| **QuerySQL** | string | 执行SQL  |No|
| **Database** | string | 库名 |No|
| **Host** | string | 连接Host地址 |No|
| **User** | string | 用户 |No|
| **QueryTime** | float | 执行耗时 |No|
| **LockTime** | float | 锁等待时间 |No|
| **RowsExamined** | int | 扫描行数 |No|
| **RowsSent** | int | 返回行数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUDACMySQLSlowLog
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=JNxccTdh
&InstanceID=gQlKshdb
&StartTime=7
&EndTime=4
&Offset=6
&Limit=8
&Database=dHNxgDXd
```

### 响应示例
    
```json
{
  "Action": "ListUDACMySQLSlowLogResponse",
  "MaxDownloadCount": 1,
  "RetCode": 0,
  "SlowLogDataSet": [
    {
      "Database": "jyDbFgUn",
      "ExecutedTime": 9.67352,
      "Host": "IjACJCaB",
      "LockTime": 4.17537,
      "QuerySQL": "VuPfvMCh",
      "QueryTime": 3.16595,
      "RowsExamined": 1,
      "RowsSend": 7,
      "User": "oUtkXfqU"
    }
  ],
  "TotalCount": 1
}
```





