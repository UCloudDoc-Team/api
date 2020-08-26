# 查看服务状态 - GetUDTSTaskStatus

## 简介

查看服务状态






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUDTSTaskStatus`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **TaskId** | string | 任务ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*StatusData*](#StatusData) | StatusData |No|

#### 数据模型


#### StatusData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MaxRetryCount** | int | 用户设置的最大失败重试次数 |No|
| **Status** | string | 任务状态, 可能的状态有Checking, Dumping, Loading, Syncing, Done, Failed 等 |No|
| **FailedMessage** | string | 当Status为Failed时, 显示失败原因 |No|
| **CurRetryCount** | int | 当前失败重试次数 |No|
| **Progress** | [*Progress*](#Progress) | Progress 全量迁移进度信息， 当类型为增量迁移时为空 |No|
| **Sync** | [*SyncData*](#SyncData) | Binlog 信息 |No|

#### Progress

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TotalCount** | int | 总条目数 |No|
| **CurCount** | int | 已迁移条目数 |No|
| **TotalDuration** | int | 估算总耗时间（单位秒） |No|
| **CurDuration** | int | 已耗时间（单位秒） |No|
| **Percentage** | float | 完成进度 |No|

#### SyncData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BinlogName** | string | Binlog 文件名， 长度不超过128字符 |**Yes**|
| **BinlogPos** | int | Binlog Pos |**Yes**|
| **ServerId** | int | 分配给UDTS task的server ID, 必须在MySQL集群中唯一 |**Yes**|
| **BinlogGTID** | string | GTID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUDTSTaskStatus
&ProjectId=org-hiny12
&TaskId=udts-ixdp441
```

### 响应示例
    
```json
{
  "Action": "GetUDTSTaskStatusResponse",
  "Data": {
    "CurRetryCount": 0,
    "MaxRetryCount": 0,
    "Progress": {
      "CurCount": 0,
      "CurDuration": 0,
      "Percentage": 0,
      "TotalCount": 0,
      "TotalDuration": 0
    },
    "Status": "Done",
    "Sync": {
      "BinlogName": "mysql-bin.000006",
      "BinlogPos": 154
    }
  },
  "Message": "",
  "RetCode": 0
}
```





