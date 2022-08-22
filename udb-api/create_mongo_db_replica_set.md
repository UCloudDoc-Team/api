# 创建DB副本集 - CreateMongoDBReplicaSet

## 简介

一键创建DB副本集






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateMongoDBReplicaSet)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateMongoDBReplicaSet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | PrimaryDB实例名称，至少6位 |**Yes**|
| **AdminPassword** | string | 管理员密码 |**Yes**|
| **DBTypeId** | string | DB类型id对应的字符串形式 mongodb-3.4,mongodb-3.6,mongodb-4.0 |**Yes**|
| **DiskSpace** | int | 磁盘空间(GB), 暂时支持20G - 3000G |**Yes**|
| **ParamGroupId** | int | DB实例使用的配置参数组id |**Yes**|
| **MemoryLimit** | int | 内存限制(MB)，目前支持以下几档 2000M/4000M/ 6000M/8000M/12000M/16000M/ 24000M/32000M/48000M/ 64000M/96000M |**Yes**|
| **Port** | int | 端口号 |**Yes**|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Month |No|
| **Quantity** | int | 购买时长(N个月)，默认值1个月。如果为0，代表购买到月底。 |No|
| **AdminUser** | string | 管理员帐户名，默认root |No|
| **BackupCount** | int | 备份策略，每周备份数量，默认7次 |No|
| **BackupTime** | int | 备份策略，备份开始时间，单位小时计，默认1点 |No|
| **BackupDuration** | int | 备份策略，备份时间间隔，单位小时计，默认24小时 |No|
| **CPU** | int | cpu核数 |No|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC的ID |No|
| **ClusterId** | string | 所属分片集群的ID |No|
| **CouponId.N** | string | CouponId.0 代表第一个代金券id，对于传入多个代金券id，后面为 CouponId.1, CouponId.2 以此类推 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DBIds** | array[string] | 返回所有副本集成员的Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateMongoDBReplicaSet
&Region=cosmAFbt
&Zone=xBxVTiMQ
&ProjectId=jrKVXipN
&Name=ydhfcdle
&AdminPassword=IMYNtZID
&DBTypeId=csTyuCveUvRbSNuMEQjiZkVcZdbiJnzuoxyZEfCPaUaMqJkcULmxcWTuGzYIaJdNtyPyfTifdEQIWGFGALkrDbHvVVAiRmdqHvtMBSsnnFRRLSOnMoAKdzSaBPxbEKrwVPZHMtivhOKqIPdMYnnbZklWtPCuHzGdwkfoPQFNAgEzLdxQieISIPOlTBdJYUfLGvCjtzICKdUaSlstsdQMvHluipqJscHJfpzqQBLYJSclSxXLtpxoiDYEjZdGmjeBsVpxcNIKIsRAHLLVLAtzGdsKbmyZphqiTHhjAHvtcmtccHYmqdeYMNLRMingKSPGgEFpqVmkvOrwAngbxiOwCDkgOVstLPwptFuYUfSzopDWOhupQAWKZDVEsADvdcBQTUXzrclMdoQhFusTDPWxmyGfWuwfzlNDgMhGaNWZkNKJQFRiDQgueKwnOvlzKfRuXGserAzG
&DiskSpace=8
&ParamGroupId=8
&MemoryLimit=2
&Quantity=7
&Port=7
&ChargeType=HDrrxEEl
&AdminUser=EbSfMBeG
&BackupCount=3
&BackupTime=2
&BackupDuration=7
&UseSSD=true
&SSDType=TnKaeTIe
&CPU=8
&InstanceType=JSduiQwk
&SubnetId=tjsNjPHZ
&VPCId=mCBucsAy
&ClusterId=LvRXciyw
&CouponId.n=uBpRaUqU
```

### 响应示例
    
```json
{
  "Action": "CreateMongoDBReplicaSetResponse",
  "DBIds": [
    "DUZMytjm"
  ],
  "RetCode": 0
}
```





