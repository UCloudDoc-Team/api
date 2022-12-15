# 获取备份列表 - ListUPgSQLBackup

## 简介

获取备份列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUPgSQLBackup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUPgSQLBackup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **InstanceID** | string | DB实例Id |**Yes**|
| **BackupType** | int | 备份类型,默认值是0(0:表示全部,1:自动备份,2:手动备份 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UPgSQLBackup*](#UPgSQLBackup)] | 备份信息列表.修参数 |**Yes**|
| **TotalCount** | int | 总个数 |**Yes**|

#### 数据模型


#### UPgSQLBackup

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 备份所在地域 |No|
| **InstanceID** | string | DB实例Id |**Yes**|
| **BackupID** | string | 备份id |**Yes**|
| **BackupName** | string | 备份名称 |No|
| **BackupStartTime** | int | 备份时间(Unix时间戳) |No|
| **BackupSize** | int | 备份文件大小(字节) |No|
| **BackupType** | int | 备份类型，手动或者自动 |No|
| **State** | string | 备份状态 (Backuping：备份中,Success:备份成功, Failed:备份失败, Expired:备份过期) |No|
| **BackupEndTime** | int | 备份完成时间(Unix时间戳) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUPgSQLBackup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=hMtkKQzD
&InstanceID=LLtYwYlt
&BackupType=5
&Offset=2
&Limit=1
```

### 响应示例
    
```json
{
  "Action": "ListUPgSQLBackupResponse",
  "Data": [
    {
      "BackupEndTime": 3,
      "BackupID": "jKlVVkmg",
      "BackupName": "qBNVHaRs",
      "BackupSize": 1,
      "BackupStartTime": 3,
      "BackupType": 3,
      "InstanceID": "SCsFwxvD",
      "Region": "fYoZJRsx",
      "State": "ciSlAoMG"
    }
  ],
  "Message": "hlvlRYaU",
  "RetCode": 0,
  "TotalCount": 3
}
```





