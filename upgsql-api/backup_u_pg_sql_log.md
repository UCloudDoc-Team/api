# 备份日志包 - BackupUPgSQLLog

## 简介

备份日志包






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BackupUPgSQLLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BackupUPgSQLLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BackupName** | string | 备份导出文件名称 |**Yes**|
| **BackupFile** | string | 备份查询结果文件名称 |**Yes**|
| **InstanceID** | string | 资源ID |**Yes**|
| **LogType** | string | 日志类型:slow(慢日志),error(错误日志) |No|
| **BeginTime** | int | 日志开始时间 |No|
| **EndTime** | int | 日志结束时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BackupUPgSQLLog
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=FQOTmBdl
&BackupName=fWJqdHUn
&BackupFile=uIkXudRf
&InstanceID=XMzvWqMx
&BeginTime=6
&EndTime=1
&BackupFile=ocLrJVzw
&BackupFile=WSBHPfUe
```

### 响应示例
    
```json
{
  "Action": "BackupUPgSQLLogResponse",
  "Message": "LCNVTOsG",
  "RetCode": 0
}
```





