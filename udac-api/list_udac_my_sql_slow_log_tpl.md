# 获取慢日志统计信息 - ListUDACMySQLSlowLogTpl

## 简介

获取慢日志统计信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUDACMySQLSlowLogTpl)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUDACMySQLSlowLogTpl`                        | **Yes** |
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
| **Limit** | int | 每页数量 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | StartTime和EndTime时间范围内，所有条目的数量 |**Yes**|
| **SlowLogTplSet** | array[[*SlowLogTpl*](#SlowLogTpl)] | 慢日志统计数据 |**Yes**|

#### 数据模型


#### SlowLogTpl

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Database** | string | 库名 |No|
| **ExecutedCount** | int | 执行次数 |No|
| **AvgQueryExecTime** | float | 平均执行时间，单位s |No|
| **MaxQueryExecTime** | float | 最大执行时间，单位s |No|
| **AvgLockTime** | float | 平均锁等待时间，单位s |No|
| **MaxLockTime** | float | 最大锁等待时间,单位s |No|
| **AvgRowsExamined** | int | 平均扫描行 |No|
| **MaxRowsExamined** | int | 最大扫描行 |No|
| **AvgRowsSent** | int | 平均返回行 |No|
| **MaxRowsSent** | int | 最大返回行 |No|
| **SQLFingerprint** | string | SQL模板指纹 |No|
| **SumQueryExecTime** | float | 执行时间总和 |No|
| **SumRowsExamined** | int | 扫描行数总和 |No|
| **SumRowsSent** | int | 返回行数总和 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUDACMySQLSlowLogTpl
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ckVRqJwD
&InstanceID=kxyXLSYe
&StartTime=3
&EndTime=3
&Offset=5
&Limit=8
&Region=cn-zj
```

### 响应示例
    
```json
{
  "Action": "ListUDACMySQLSlowLogTplResponse",
  "RetCode": 0,
  "SlowLogTplSet": [
    {
      "AvgLockTime": 4.91274,
      "AvgQueryExecTime": 1.28743,
      "AvgRowsExamined": 5,
      "AvgRowsSent": 9,
      "Database": "eRaBdDdo",
      "ExecutedCount": 4,
      "MaxLockTime": 2.89938,
      "MaxQueryExecTime": 3.12243,
      "MaxRowsExamined": 8,
      "MaxRowsSent": 5,
      "SQLFingerprint": "vkEZUspV"
    }
  ],
  "TotalCount": 4
}
```





