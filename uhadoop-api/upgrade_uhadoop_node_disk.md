# 扩容集群节点磁盘 - UpgradeUHadoopNodeDisk

## 简介

扩容集群节点磁盘






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpgradeUHadoopNodeDisk)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpgradeUHadoopNodeDisk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NodeRole** | string | 节点角色，值为master\|core\|task之一 |**Yes**|
| **DataDiskSize** | int | 新的数据盘磁盘大小 |**Yes**|
| **InstanceId** | string | 实例ID |**Yes**|
| **NodeNames.N** | string | 节点名称集合,当NodeRole不为master时必填 |No|
| **BootDiskSize** | int | 系统盘磁盘大小，仅支持云盘裸金属机型（系统盘和数据盘数值同时增加、只会处理系统盘参数） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpgradeUHadoopNodeDisk
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=MeygKDbC
&ClusterInstanceId=QFiXmrsT
&NodeRole=GcYLXWQp
&NodeNames.n=VAtKCAoU
&DataDiskSize=3
&ChargeType=Year
&BootDiskSize=7
```

### 响应示例
    
```json
{
  "Action": "UpgradeUHadoopNodeDiskResponse",
  "Message": "JGpSwjEc",
  "RetCode": 0
}
```





