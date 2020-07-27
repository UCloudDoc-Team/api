# 备份云数据库 - BackupUDBInstance

## 简介

备份UDB实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BackupUDBInstance)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BackupUDBInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **DBId** | string | DB实例Id,该值可以通过DescribeUDBInstance获取 |**Yes**|
| **BackupName** | string | 备份名称 |**Yes**|
| **UseBlacklist** | boolean | 是否使用黑名单备份，默认false |No|
| **BackupMethod** | string | 使用的备份方式。（快照备份即物理备份。注意只有SSD版本的mysql实例支持设置为snapshot） |No|
| **Blacklist** | string | 备份黑名单列表，以 ; 分隔。注意：只有逻辑备份下备份黑名单才生效，快照备份备份黑名单下无效 |No|
| **ForceBackup** | boolean | true表示逻辑备份时是使用 --force 参数，false表示不使用 --force 参数。物理备份此参数无效。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BackupUDBInstance    
&Region=cn-bj2
&DBId=udbha-xxxx
&BackupName=master-backup
&BackupMethod=snapshot
&Blacklist=ZScuaauv
&ForceBackup=false
```

### 响应示例
    
```json
{
  "Action": "BackupUDBInstanceResponse",
  "RetCode": 0
}
```





