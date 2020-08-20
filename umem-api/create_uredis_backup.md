# 创建主备Redis备份 - CreateURedisBackup

## 简介

创建主备Redis备份






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateURedisBackup)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateURedisBackup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **GroupId** | string | 资源id |**Yes**|
| **BackupName** | string | 请求创建组的名称 (范围[6-63],只能包含英文、数字以及符号-和_) |**Yes**|
| **SlaveZone** | string | 跨机房URedis，slave所在可用区（必须和Zone在同一Region，且不可相同） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BackupId** | string | 备份id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateURedisBackup
&Region=cn-zj
&Zone=cn-zj-01
&GroupId=资源ID
&BackupName=XMhgklHk
&RegionFlag=false
&ProjectId=uBUqXisa
&SlaveZone=LgjUXVen
```

### 响应示例
    
```json
{
  "Action": "CreateURedisBackupResponse",
  "RetCode": 0
}
```





