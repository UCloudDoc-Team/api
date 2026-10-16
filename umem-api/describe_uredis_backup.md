# 查询主备redis备份 - DescribeURedisBackup

## 简介

查询主备redis备份






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeURedisBackup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeURedisBackup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **GroupId** | string | 组的ID，如果不传RegionType,GroupId为必传项 |No|
| **Offset** | int | 分页显示的起始偏移, 默认值为0 |No|
| **Limit** | int | 分页显示的条目数, 默认值为10 |No|
| **SlaveZone** | string | 跨机房URedis，slave所在可用区（必须和Zone在同一Region，且不可相同） |No|
| **RegionType** | string | 用于区分跨可用备份以及普通备份。默认为normal。<br />跨可用则分为(source, target) |No|
| **BackupId** | string | 备份Id，若传入，则只返回该BackupId的备份信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 用户名下总的备份个数 |No|
| **DataSet** | array[[*URedisBackupSet*](#URedisBackupSet)] | 备份列表 参见 URedisBackupSet |No|

#### 数据模型


#### URedisBackupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区，参见[可用区列表](api/summary/regionlist) |No|
| **BackupId** | string | 备份ID |No|
| **GroupId** | string | 对应的实例ID |No|
| **GroupName** | string | 组名称 |No|
| **BackupName** | string | 备份的名称 |No|
| **BackupTime** | int | 备份时间 (UNIX时间戳) |No|
| **BackupSize** | int | 备份文件大小, 以字节为单位 |No|
| **BackupType** | string | 备份类型: Manual 手动 Auto 自动 |No|
| **State** | string | 备份的状态: Backuping 备份中 Success 备份成功 Error 备份失败 Expired 备份过期 |No|
| **SrcRegionName** | string | 跨地域备份源地域 |No|
| **DstRegionName** | string | 跨地域备份目标地域 |No|
| **MemorySize** | int | 源实例容量大小 |No|
| **RedisVersion** | string | 源实例Redis版本 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeURedisBackup
&Region=cn-bj2
&SlaveZone=IRVyPYOd
&RegionType=JaAnSlXu
&BackupId=UwszgeYW
&BackupId=UUBzedWb
```

### 响应示例
    
```json
{
  "Action": "DescribeURedisBackupResponse",
  "DataSet": [
    {
      "BackupId": "a75XXXa9-d9e1-4d38-9XX1-aecad464XXX5",
      "BackupName": "sgbf_XXXXXX",
      "BackupSize": 18,
      "BackupTime": 1529912363,
      "BackupType": "Manual",
      "GroupId": "uredis-grXXXz",
      "GroupName": "zbredia_XXXXX",
      "State": "Success",
      "Zone": "cn-bj2-04"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





