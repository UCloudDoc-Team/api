# 创建一个实例 - CreateUKafkaInstance

## 简介

创建一个ukafka实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUKafkaInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUKafkaInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **FrameworkVersion** | string | kafka版本，支持的版本可通过ListUKafkaFrameworkVersion 接口返回字段的FrameworkVersions获取 |**Yes**|
| **VPCId** | string | VPCID |**Yes**|
| **SubnetId** | string | 子网 ID |**Yes**|
| **ChargeType** | string | 付费方式 |**Yes**|
| **NodeType** | string | 机型，支持的机型可通过GetUKafkaNodeType 接口返回的InstanceTypeSet[].InstanceTypeName |**Yes**|
| **DiskSize** | int | 数据盘大小。支持范围根据GetUKafkaNodeType 接口返回的InstanceTypeSet[].MaxDiskSize 和MinDiskSize获取 |**Yes**|
| **InstanceName** | string | 实例名，可自定义 |**Yes**|
| **BusinessId** | string | 业务组，默认Default |No|
| **Quantity** | string | 实例数量，默认 1 |No|
| **NodeCount** | int | 集群节点数量。默认 3 节点 |No|
| **LogRetentionHours** | string | kafka 日志保存时间，支持范围[1,240]。默认 72 小时 |No|
| **DiskControllerType** | string | 磁盘管理方式,支持值：NONE、CLEAN。默认值：NONE |No|
| **DiskThreshold** | string | 磁盘清理阈值，支持范围[70,90]。DiskControllerType 为CLEAN 时必填。默认值 90 |No|
| **IsSecurityEnabled** | string | 是否开启安全组，支持"true","false"，默认 false |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceId** | string | 实例资源 ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUKafkaInstance
&ProjectId=org-xts2j0
&Zone=cn-bj2-05
&Region=cn-bj2
&ClusterInstanceName=barfoo
&LoginMode=Password
&Framework=Kafka
&Password=dW5kZWZpbmVk
&FrameworkVersion=1.1.1
&ChargeType=Dynamic
&Quantity=1
&InstanceGroupConfig=N1-large#3
&Tag=Default
&SubnetId=subnet-xo4nvk
&VPCId=uvnet-erxgwh
&Concurrency=30
&ClusterConfigs.0=log.retention.hours#72
&ClusterConfigs.1=DiskThreshold#80
&ClusterConfigs.2=DiskControllerType#CLEAN
&Action=CreateUKafkaInstance
&_user=pan.ma%40ucloud.cn
&_timestamp=1545630237660
&ClusterInstanceName=JazwZJAT
&Quantity=RtALqSOr
&ChargeType=xoPAsVKz
&NodeType=BuJplpPu
&NodeNum=szuCxYyA
&SubnetId2=tYpxLNMB
&VPCID2=WUEuEXCe
&LogRetentionHours=lMlcaGNx
&DiskControllerType=POJjFcOU
&DiskSize=AdTgjJLD
&DiskThreshold=NZHiwKFm
&IsSecurityEnabled=qsHobWJf
```

### 响应示例
    
```json
{
  "Action": "CreateUKafkaInstanceResponse",
  "ClusterInstanceId": "ukafka-g5s1nd",
  "Message": "exoIIFmP",
  "RetCode": 0
}
```





