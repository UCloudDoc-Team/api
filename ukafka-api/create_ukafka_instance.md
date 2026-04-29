# 创建实例 - CreateUKafkaInstance

## 简介

创建实例接口。<br /><br /> 创建实例前需要按以下步骤准备必要参数：<br /><br /> 1.获取Region（地域）和 Zone（可用区），访问链接：https://docs.ucloud.cn/api/summary/regionlist 可以获取所有支持的地域和可用区；<br /><br /> 2.获取FrameworkVersion，访问链接：https://docs.ucloud.cn/api/ukafka-api/list_ukafka_framework_version，响应字段的FrameworkVersions[N].Version是支持的 Kafka 版本；<br /><br /> 3.ChargeType付费类型，可用值：Dynamic为按小时付费，Month为按月付费，Year为按年付费；<br /><br /> 4.获取NodeType机型详情，访问链接：https://docs.ucloud.cn/api/ukafka-api/get_ukafka_node_type，响应字段的NodeTypeSet[N].NodeTypeName是支持的所有机型；<br /><br /> 5.获取DiskSize磁盘大小范围 ，访问链接：https://docs.ucloud.cn/api/ukafka-api/get_ukafka_node_type，该接口响应字段的NodeTypeSet[N].MinDiskSize和NodeTypeSet[N].MaxDiskSize是磁盘大小的取值范围；6.InstanceName，自定义输入实例名称，只能包含中英文、数字以及- _ .






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
| **InstanceName** | string | 实例名，可自定义。只能包含中英文、数字以及- _ . |**Yes**|
| **BusinessId** | string | 业务组，默认Default |No|
| **Quantity** | string | 实例数量，默认 1 |No|
| **NodeCount** | int | 实例节点数量。默认 3 节点 |No|
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
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=UTnNmyFz
&FrameworkVersion=NCaSSrbA
&VPCId=Xersagmc
&SubnetId=EbTTLPWW
&ChargeType=jHScnWTI
&NodeType=cjEAuPWT
&DiskSize=3
&InstanceName=VFRMQMkS
&BusinessId=ySLTzIEl
&Quantity=CIZwhKZG
&NodeCount=3
&LogRetentionHours=ZkwzUota
&DiskControllerType=pJPWwZjQ
&DiskThreshold=FTegxrIv
&IsSecurityEnabled=ZijHghwt
```

### 响应示例
    
```json
{
  "Action": "CreateUKafkaInstanceResponse",
  "InstanceId": "VtVVhchC",
  "Message": "jvKmwNEU",
  "RetCode": 0
}
```





