# 卸载删除云硬盘 - DetachDeleteUDisk

## 简介

卸载删除某个已经挂载在指定UHost实例上的UDisk






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DetachDeleteUDisk)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DetachDeleteUDisk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UDiskId** | string | 需要卸载的UDisk实例ID |**Yes**|
| **UHostId** | string | UHost实例ID。【UHostId和HostId必须选填一个，本字段即将废弃，建议使用HostId】 |No|
| **HostId** | string | Host实例ID |No|
| **DeleteSnapshotService** | string | 是否删除快照服务。Yes：删除，No：不删除，默认值：Yes。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UHostId** | string | 卸载的UHost实例ID。【即将废弃，建议使用HostId】 |No|
| **HostId** | string | 卸载的Host实例ID |No|
| **UDiskId** | string | 卸载删除的UDisk实例ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DetachDeleteUDisk
&Region=jUjENnRU
&Zone=jyQMsime
&ProjectId=ysaijOEv
&UHostId=GEtUmxtW
&HostId=WcdKcRsT
&UDiskId=LaaTtNLf
&HostProduct=PlcPMTyc
&CloseSnapshotService=EhlaHTFE
```

### 响应示例
    
```json
{
  "Action": "DetachDeleteUDiskResponse",
  "HostId": "zBFpZJeX",
  "RetCode": 0,
  "UDiskId": "ZEUGkdOT",
  "UHostId": "pbVjIMWx"
}
```





