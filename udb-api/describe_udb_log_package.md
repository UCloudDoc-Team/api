# 列表UDB实例日志备份信息 - DescribeUDBLogPackage

## 简介

列表UDB实例binlog或slowlog或errorlog备份信息

?> 不支持新版（NVMe型）MongoDB/PostgreSQL， 新版（NVMe型）MongoDB/PostgreSQL请使用对应产品的API




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBLogPackage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBLogPackage`                        | **Yes** |
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
| **Type** | int | 需要列出的备份文件类型，每种类型的值如下： 2 代表 BINLOG_BACKUP； 3 代表 SLOW_QUERY_BACKUP； 4 代表 ERRORLOG_BACKUP。 |No|
| **Types.N** | int | Types作为Type的补充，支持多值传入，可以获取多个类型的日志记录，如：Types.0=2&Types.1=3 |No|
| **DBId** | string | DB实例Id，如果指定，则只获取该db的备份信息; 当Type为2时必填 |No|
| **BeginTime** | int | 过滤条件:起始时间(时间戳) |No|
| **EndTime** | int | 过滤条件:结束时间(时间戳) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*LogPackageDataSet*](#LogPackageDataSet)] | 备份信息 参见LogPackageDataSet |No|
| **TotalCount** | int | 备份总数，如果指定dbid，则是该db备份总数 |No|

#### 数据模型


#### LogPackageDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 所在可用区 |No|
| **BackupId** | int | 备份id |No|
| **BackupName** | string | 备份名称 |No|
| **BackupTime** | int | 备份时间 |No|
| **BackupSize** | int | 备份文件大小 |No|
| **BackupType** | int | 备份类型，包括2-binlog备份，3-slowlog备份 |No|
| **BinlogType** | string | binlog备份类型 Manual //手动备份 Auto //自动备份 |No|
| **State** | string | 备份状态 Backuping // 备份中 Success // 备份成功 Failed // 备份失败 Expired // 备份过期 |No|
| **DBId** | string | dbid |No|
| **DBName** | string | 对应的db名称 |No|
| **BackupZone** | string | 跨可用区高可用备库所在可用区 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBLogPackage
&Region=cn-bj2
&Zone=cn-bj2-04
&Offset=0
&Limit=20
&Type=2
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBLogPackageResponse",
  "DataSet": [
    {
      "BackupId": 45264,
      "BackupName": "undefined",
      "BackupSize": 339,
      "BackupTime": 1329815192,
      "BackupType": 2,
      "BackupZone": "",
      "DBId": "udbha-xxxxxx",
      "DBName": "test_linshi",
      "State": "Success",
      "Zone": "cn-bj2-04"
    },
    {
      "BackupId": 39,
      "BackupName": "rizhi_01",
      "BackupSize": 10670,
      "BackupTime": 1439430490,
      "BackupType": 2,
      "BackupZone": "",
      "DBId": "udb-xxxxxx",
      "DBName": "annian_2g",
      "State": "Success",
      "Zone": "cn-bj2-05"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





