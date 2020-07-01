# 创建从库 - CreateUDBSlave

## 简介

创建UDB实例的slave






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDBSlave)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDBSlave`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SrcId** | string | master实例的DBId,该值可以通过DescribeUDBInstance获取 |**Yes**|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **Port** | int | 端口号 |No|
| **UseSSD** | boolean | 是否使用SSD，默认为true |No|
| **SSDType** | string | SSD类型，可选值为"SATA"、"PCI-E"、“NVMe”，如果UseSSD为true ，则必选 |No|
| **IsLock** | boolean | 是否锁主库，默认为true |No|
| **InstanceMode** | string | UDB实例部署模式，可选值如下：<br />Normal: 普通单点实例<br />HA: 高可用部署实例 |No|
| **MemoryLimit** | int | 内存限制(MB)，目前支持以下几档 1000M/2000M/4000M/ 6000M/8000M/12000M/16000M/ 24000M/32000M/48000M/ 64000M/96000M/128000M/192000M/256000M/320000M |No|
| **DiskSpace** | int | 磁盘空间(GB), 暂时支持20G - 3000G（API支持，前端暂时只开放内存定制） |No|
| **InstanceType** | string | UDB实例类型：Normal、SATA_SSD、NVMe_SSD |No|
| **SubnetId** | string | 子网ID（如果不传用默认子网） |No|
| **VPCId** | string | VPCID（如果不传用默认的VPC） |No|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认和主库保持一致 |No|
| **Quantity** | int | 购买时长，默认默认和主库保持一致 |No|
| **ParamGroupId** | int | DB实例使用的配置参数组id，默认和主库保持一致 |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DBId** | string | 创建slave的DBId |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDBSlave 
&Region=cn-bj2
&SrcId=udb-xxxxx
&Name=udb-xxxxxxx-slave
&Port=3306     
&MemoryLimit=4
&DiskSpace=4
&SubnetId=CSKpxQOp
&SubnetId=ICAmjpca
&VPCId=iGLJHujL
&ChargeType=RyAdXrgR
&Quantity=5
&ChargeType=IPwSWCtM
&Quantity=5
&ParamGroupId=4
```

### 响应示例
    
```json
{
  "Action": "CreateUDBSlaveResponse",
  "DBId": "udb-xxxxxx",
  "RetCode": 0
}
```





