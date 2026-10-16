# 获取主备Redis备份下载链接 - DescribeURedisBackupURL

## 简介

获取主备Redis备份下载链接






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeURedisBackupURL)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeURedisBackupURL`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BackupId** | string | 备份ID |**Yes**|
| **RegionFlag** | boolean | 是否是跨机房URedis(默认false) |No|
| **GroupId** | string | 实例ID |No|
| **SlaveZone** | string | 跨机房URedis，slave所在可用区（必须和Zone在同一Region，且不可相同） |No|
| **IsCrossRegion** | boolean | 默认为false,true时代表查询跨地域备份URL |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BackupURL** | string | [即将下线,请使用BackupPath] |No|
| **BackupPath** | string | 备份文件公网的地址 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeURedisBackupURL
&Region=cn-bj2
&Zone=cn-bj2-04
&BackupId=00XXX68c-c7f5-XX52-9eac-dXXXXXXX8f0e1
&GroupId=mfweUQnQ
&SlaveZone=VlwscEJR
&IsCrossRegion=false
```

### 响应示例
    
```json
{
  "Action": "DescribeURedisBackupURLResponse",
  "BackupPath": "KgVuXeBu",
  "BackupURL": "http://umembXXXXXup-9001.cn-bj.ilXXXXeos.com/uredis-XXXXbz/sgbf_xxxxxx-a75b24a9-d9e1-4d38-9dc1-aecad464XXX45?UCloudPublicKey=ucloudXXX@ucloud.cn142615241XXXX604875621\u0026Expires=1529927068\u0026Signature=sbH+QOWbtxXXXX6z5o6HBxrOcU=\n",
  "InnerBackupPath": "zeAzhTZt",
  "RetCode": 0
}
```





