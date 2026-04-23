# 获取节点类型信息 - GetUHadoopNodeType

## 简介

获取节点类型信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUHadoopNodeType)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUHadoopNodeType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **FrameworkVersion** | string | 框架版本，例如3.2.1-udh3.0，通过ListUHadoopFrameworkApp接口获取 |No|
| **NodeRole** | string | 角色，master\|core\|task |No|
| **NodeType** | string | 机型名称 |No|
| **Framework** | string | 框架，例如Hadoop\|MR\|HDFS\|StarRocks<br />，<br />Hadoop框架包含存储与计算服务，<br />MR集群包含计算服务，<br />HDFS只包含存储服务，StarRocks为StarRocks集群 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceTypeSet** | array[[*InstanceType*](#InstanceType)] | 类型信息 |**Yes**|
| **MetaDataUDBUsable** | boolean | 当前可用区是否支持元数据库使用UDB |No|
| **HostTypeSupportNodeType** | string | 机型可支持的节点类型 |No|

#### 数据模型


#### InstanceType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NodeType** | string | 机型名称 |**Yes**|
| **HostType** | string | 机型种类，可选Outstanding(快杰机型)\|General(普通机型)\|BareMetal(裸金属机型)\|GPU(GPU机型)四种类型 |**Yes**|
| **SuitableRole** | array[string] | 可用的节点类型，值为core\|task\|master之一 |**Yes**|
| **CPU** | string | cpu大小 |**Yes**|
| **CPUToMemoryRatio** | string | cpu内存比 |**Yes**|
| **Memory** | string | 内存大小 |**Yes**|
| **DiskSet** | array[[*DiskSet*](#DiskSet)] | 磁盘信息 |**Yes**|
| **IsUsable** | string | 是否可用,该机型是否支持创建 |**Yes**|
| **IsOpenSecgroup** | string | 是否支持开启安全组 |No|
| **GpuType** | string | GPU型号 |No|
| **GpuCount** | int | GPU数量 |No|

#### DiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Size** | int | 总磁盘大小 |**Yes**|
| **Type** | string | 磁盘角色，分Data数据盘和Boot系统盘 |**Yes**|
| **DiskType** | array[string] | 可支持的磁盘类型 |**Yes**|
| **SingleDiskSize** | int | 单块盘大小 |No|
| **DiskNum** | int | 磁盘数量 |No|
| **DiskMaxNum** | string | 最大磁盘数量 |No|
| **DiskMaxSize** | string | 最大单块盘容量，单位GB |No|
| **DiskMinNum** | string | 最小磁盘数量 |No|
| **DiskMinSize** | string | 最小单块盘容量，单位GB |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUHadoopNodeType
&Region=cn-zj
&Zone=cn-zj-01
&InstanceRole=EZCbCeuC
&InstanceType=tBAGIrVG
&UDDPFramework=OTKERJhX
&FrameworkVersion=QdaJHPdO
```

### 响应示例
    
```json
{
  "Action": "GetUHadoopNodeTypeResponse",
  "HostTypeSupportDiskType": {},
  "InstanceTypeSet": [
    "yUPLaHEL",
    "oShfPgxP",
    "jDqKpRMJ",
    "qIusilLv",
    "MZfvDmjX",
    "rLZIzIOa",
    "oNdctVSR"
  ],
  "Message": "bQJiBLVR",
  "MetaDataUDBUsable": true,
  "RetCode": 0,
  "SupportDiskType": [
    "bGdIGhlo"
  ]
}
```





