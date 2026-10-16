# 修改UDB自动备份策略 - UpdateUDBInstanceBackupStrategy

## 简介

修改UDB自动备份策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateUDBInstanceBackupStrategy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUDBInstanceBackupStrategy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DBId** | string | 主节点的Id |**Yes**|
| **BackupTime** | int | 备份的整点时间，范围[0,23] |No|
| **BackupDate** | string | 备份时期标记位。共7位，每一位为一周中一天的备份情况，0表示关闭当天备份，1表示打开当天备份。最右边的一位为星期天的备份开关，其余从右到左依次为星期一到星期六的备份配置开关，每周必须至少设置两天备份。例如：1100000表示打开星期六和星期五的备份功能 |No|
| **ForceDump** | boolean | 当导出某些数据遇到问题后，是否强制导出其他剩余数据<br />默认是false<br />需要同时设置BackupDate字段 |No|
| **BackupMethod** | string | 选择默认的备份方式，可选nobackup表示不备份， snapshot 表示使用快照备份，logic 表示使用逻辑备份。需要同时设置BackupDate字段。（快照备份即物理备份。SSD版本的mysql实例支持设置为snapshot，NVMe版本的mysql实例支持设置为xtrabackup） |No|
| **UserTokenID** | string | 自动备份转存到用户自己的bucket 的tokenid， 需要用户自己自己设置权限 |No|
| **UserBucket** | string | 自动备份转存到用户自己的bucket名称，要包含到对应的token id里 |No|
| **EnableBinlogBackup** | boolean | 是否开启binlog备份, 默认为未开启 |No|
| **BinlogRemoteSaveDays** | int | 远端binlog保存时长(天) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.spark.ucloud.cn/?Action=UpdateUDBInstanceBackupStrategy  
&Region=cn-bj2
&ProjectId=7                          
&DBId=udb-xxx
&BackupTime=5
&BackupDate=0011111
&BackupMethod=rjlwkIlW
&UserTokenID=hCBIvgmm
&UserBucket=eInaAosL
&EnableBinlogBackup=true
&BinlogRemoteSaveDays=4
```

### 响应示例
    
```json
{
  "Action": "UpdateUDBInstanceBackupStrategyResponse",
  "RetCode": 0
}
```





