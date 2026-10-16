# 获取备份列表 - DescribeUDBBackup

## 简介

列表UDB实例备份信息.Zone不填表示多可用区，填代表单可用区






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBBackup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


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
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 分页显示的起始偏移，列表操作则指定 |**Yes**|
| **Limit** | int | 分页显示的条目数，列表操作则指定 |**Yes**|
| **DBId** | string | DB实例Id，如果指定，则只获取该db的备份信息 该值可以通过DescribeUDBInstance获取 |No|
| **BackupType** | int | 备份类型,取值为0或1，0表示自动，1表示手动 |No|
| **BeginTime** | int | 过滤条件:起始时间(Unix时间戳) |No|
| **EndTime** | int | 过滤条件:结束时间(Unix时间戳) |No|
| **ClassType** | string | 如果未指定GroupId，则可选是否选取特定DB类型的配置(sql, nosql, postgresql, sqlserver) |No|

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
| **Zone** | string | 备份所在可用区 |No|
| **BackupId** | int | 备份id |No|
| **BackupName** | string | 备份名称 |No|
| **BackupTime** | int | 备份时间(Unix时间戳) |No|
| **BackupSize** | int | 备份文件大小(字节) |No|
| **BackupType** | int | 备份类型,取值为0或1,0表示自动，1表示手动 |No|
| **State** | string | 备份状态 Backuping // 备份中 Success // 备份成功 Failed // 备份失败 Expired // 备份过期 |No|
| **ErrorInfo** | string | 备份错误信息 |No|
| **DBId** | string | dbid |No|
| **DBName** | string | 对应的db名称 |No|
| **BackupZone** | string | 跨机房高可用备库所在可用区 |No|
| **BackupEndTime** | int | 备份完成时间(Unix时间戳) |No|
| **MD5** | string | 备份文件的MD5值，备份完成后显示，备份中或备份失败时为空,目前只支持Mysql NVMe机型与Mongo |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBBackup
&Region=cn-bj2
&Offset=0
&Limit=20
&BackupId=1
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBBackupResponse",
  "DataSet": [
    {
      "BackupEndTime": 1329867185,
      "BackupId": 296133,
      "BackupName": "system backup",
      "BackupSize": 167066,
      "BackupTime": 1429867144,
      "BackupType": 0,
      "BackupZone": null,
      "DBId": "udbha-xxxxxx",
      "DBName": "frombf-hassd-56",
      "ErrorInfo": "",
      "State": "Success",
      "Zone": "cn-bj2-02"
    },
    {
      "BackupEndTime": 1429859800,
      "BackupId": 29534,
      "BackupName": "system backup",
      "BackupSize": 3105731,
      "BackupTime": 1429859724,
      "BackupType": 0,
      "BackupZone": null,
      "DBId": "udb-xxxxx",
      "DBName": "test_linshi",
      "ErrorInfo": "",
      "State": "Success",
      "Zone": "cn-bj2-02"
    }
  ],
  "RetCode": 0,
  "TotalCount": 180
}
```





