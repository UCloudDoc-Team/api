# 更改主备Redis备份策略 - UpdateURedisBackupStrategy

## 简介

URedisBackupStrategy






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateURedisBackupStrategy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateURedisBackupStrategy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **GroupId** | string | 组的ID |**Yes**|
| **BackupTime** | string | 备份时间，默认为0 |No|
| **AutoBackup** | string | 是否打开默认备份功能。enable(打开)，disable(关闭)，默认enable |No|
| **SlaveZone** | string | 跨机房URedis，slave所在可用区（必须和Zone在同一Region，且不可相同） |No|
| **OperationType** | string | 操作类型，不传默认为normal(即操控自动备份打开以及时间)，modify（修改跨地域备份策略）,close(关闭跨地域备份策略) |No|
| **DstRegion** | string | 跨可用备份目标地域（当Operation为modify时必选） |No|
| **SaveDays** | int | 保存天数（当Operation为modify时必选） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateURedisBackupStrategy
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=VxWfsZys
&GroupId=rHCjeKTH
&AutoBackup=mtVDaYvy
&AutoBackup=dWyotcjn
&BackupTime=Sdchjvlm
&SlaveZone=DHihOSqO
&Operation=kBNHHpHu
&TargetRegionId=6
&SaveDays=3
&SrcRegion=dfueMRGC
&OperationType=wJxZJSff
```

### 响应示例
    
```json
{
  "Action": "UpdateURedisBackupStrategyResponse",
  "RetCode": 0
}
```





