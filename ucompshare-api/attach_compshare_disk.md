# 挂载云硬盘 - AttachCompshareDisk

## 简介

将一个可用的UDisk挂载到某台主机上






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AttachCompshareDisk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UDiskId** | string | 需要挂载的UDisk实例ID. |**Yes**|
| **UHostId** | string | UHost实例ID。【UHostId和HostId必须选填一个，本字段即将废弃，建议使用HostId】 |No|
| **EnableCrossPodAttach** | string | 是否允许跨pod挂载（Yes：允许跨pod挂载，No：不允许跨pod挂载，不填默认No） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AttachCompshareDisk
&Region=RZtAifyn
&Zone=VezeLsPy
&ProjectId=HDcNnqEz
&UDiskId=cCuExVUm
&UHostId=AMmpLYPI
&MultiAttach=JCPHqHxX
&HostId=pAHZprdH
&EnableCrossPodAttach=wZOkjnYy
```

### 响应示例
    
```json
{
  "Action": "AttachCompshareDiskResponse",
  "DeviceName": "LGuoTdbi",
  "HostId": "HZpbWQrR",
  "RetCode": 0,
  "UDiskId": "eVXTvqUP",
  "UHostId": "zQhymdCI"
}
```





