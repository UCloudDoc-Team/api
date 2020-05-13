# 获取备份列表 - DescribeUDBBackup

## 简介

列表UDB实例备份信息





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBBackup)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBBackup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | int | 分页显示的起始偏移，列表操作则指定 |**Yes**|
| **Limit** | int | 分页显示的条目数，列表操作则指定 |**Yes**|
| **DBId** | string | DB实例Id，如果指定，则只获取该db的备份信息 该值可以通过DescribeUDBInstance获取 |No|
| **BackupType** | int | 备份类型,取值为0或1，0表示自动，1表示手动 |No|
| **BeginTime** | int | 过滤条件:起始时间(Unix时间戳) |No|
| **EndTime** | int | 过滤条件:结束时间(Unix时间戳) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDBBackupSet*](#UDBBackupSet)] | 备份信息 参照UDBBackupSet |No|
| **TotalCount** | int | 满足条件备份总数，如果指定dbid，则是该db备份总数 |No|

#### 数据模型


#### UDBBackupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackupId** | int | 备份id |No|
| **BackupName** | string | 备份名称 |No|
| **BackupTime** | int | 备份时间(Unix时间戳) |No|
| **BackupSize** | int | 备份文件大小(字节) |No|
| **BackupType** | int | 备份类型,取值为0或1,0表示自动，1表示手动 |No|
| **State** | string | 备份状态 Backuping // 备份中 Success // 备份成功 Failed // 备份失败 Expired // 备份过期 |No|
| **DBId** | string | dbid |No|
| **DBName** | string | 对应的db名称 |No|
| **Zone** | string | 备份所在可用区 |No|
| **BackupZone** | string | 跨机房高可用备库所在可用区 |No|
| **BackupEndTime** | int | 备份完成时间(Unix时间戳) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBBackup
&Region=cn-bj2
&Offset=0
&Limit=20
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBBackupResponse",
  "DataSet": [
    {
      "BackupId": 57214,
      "BackupName": "system backup",
      "BackupSize": 138571,
      "BackupTime": 1410894157,
      "BackupType": 0,
      "DBId": "c1d1d90d-e039-4483-8cd6-b31614d71817",
      "DBName": "testtest",
      "State": "Backuping"
    },
    {
      "BackupId": 57215,
      "BackupName": "system backup",
      "BackupSize": 138571,
      "BackupTime": 1412894156,
      "BackupType": 0,
      "DBId": "c1d1d90d-e039-4483-8cd6-b31614d71817",
      "DBName": "testtest",
      "State": "Success"
    }
  ],
  "RetCode": 0,
  "TotalCount": 7
}
```





