# 创建从库 - CreateUDBSlave

## 简介

创建UDB实例的slave






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDBSlave)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


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
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SrcId** | string | master实例的DBId,该值可以通过DescribeUDBInstance获取 |**Yes**|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **Port** | int | 端口号 |No|
| **SSDType** | string | 仅对主为SSD型实例有效。 可选值"SATA","NVMe" |No|
| **IsLock** | boolean | 是否锁主库，默认为true |No|
| **MemoryLimit** | int | 内存限制(MB)，目前支持以下几档 2000M/4000M/ 6000M/8000M/12000M/16000M/ 24000M/32000M/48000M/ 64000M/96000M/128000M/192000M/256000M/320000M |No|
| **DiskSpace** | int | 磁盘空间(GB), 暂时支持20G - 3000G（API支持，前端暂时只开放内存定制） |No|
| **SubnetId** | string | 子网ID（如果不传用默认子网） |No|
| **VPCId** | string | VPCID（如果不传用默认的VPC） |No|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认和主库保持一致 |No|
| **Quantity** | int | 购买时长，默认默认和主库保持一致 |No|
| **ParamGroupId** | int | DB实例使用的配置参数组id，默认和主库保持一致 |No|
| **IsCreatePhysically** | boolean | 使用物理方式创建从库，目前仅限创建快杰从库，默认为false |No|
| **DelaySeconds** | int | 设置从库的延时复制时长（单位秒） |No|
| **SpecificationType** | int | 实例计算规格类型，0或不传代表使用内存方式购买，1代表使用内存-cpu可选配比方式购买，需要填写MachineType |No|
| **MachineType** | string | 规格类型ID,当SpecificationType为1时有效 |No|
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
&IsCreatePhysically=false
&DelaySeconds=6
&UseSSD=true
&SSDType=GnsgKEyT
&SpecificationType=cYBUpmpw
&MachineType=EEMCUisF
```

### 响应示例
    
```json
{
  "Action": "CreateUDBSlaveResponse",
  "DBId": "udb-xxxxxx",
  "RetCode": 0
}
```





