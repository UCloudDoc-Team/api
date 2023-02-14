# 创建主备redis - CreateURedisGroup

## 简介

创建主备redis






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateURedisGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateURedisGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 请求创建组的名称 (范围[6-63],只能包含英文、数字以及符号-和_) |**Yes**|
| **HighAvailability** | string | 是否开启高可用,enable或disable |**Yes**|
| **Size** | int | 每个节点的内存大小,单位GB,默认1GB,目前仅支持1/2/4/8/16/32,六种 |No|
| **AutoBackup** | string | 是否自动备份,enable或disable，默认disable |No|
| **BackupTime** | int | 自动备份开始时间,范围[0-23],默认3点 |No|
| **ConfigId** | string | 配置ID,目前支持 4.0版本配置ID:"6c9298a3-9d7f-428c-b1d0-e87ab3b8a1ea", 5.0版本配置ID:"3cdeeb90-dcbf-46e8-95cd-a05d8860a22c",6.0版本配置ID:"1d990520-aac8-4e0f-9384-f58611e8eb28",7.0版本配置ID:"48dcf534-db41-11ec-a1a6-52670028d520",默认版本4.0,从备份创建为必传项 |No|
| **Version** | string | Redis版本信息(详见DescribeURedisVersion返回结果),默认版本4.0 |No|
| **ChargeType** | string | 计费模式，Year , Month, Dynamic 默认: Month |No|
| **Quantity** | int | 购买时长，默认为1 |No|
| **Tag** | string | 业务组名称 |No|
| **Password** | string | 初始化密码,需要 base64 编码 |No|
| **BackupId** | string | 有此项代表从备份中创建，无代表正常创建 |No|
| **SlaveZone** | string | 跨机房URedis，slave所在可用区（必须和Zone在同一Region，且不可相同） |No|
| **MasterGroupId** | string | Master Redis Group的ID，创建只读Slave时，必须填写 |No|
| **EnableIpV6** | boolean | 是否创建使用ipv6 资源， 默认为false， 或者不填， 创建ipv6为true |No|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC的ID |No|
| **HighPerformance** | boolean | 是否创建高性能Redis， 默认为false， 或者不填， 创建高性能为true |No|
| **CouponId** | string | 代金券ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **GroupId** | string | 创建的组ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateURedisGroup
&Region=cn-bj2
&Zone=cn-bj2-04
&Name=zb_redisXXXX
&Protocol=GSlQEcQU
&EnableIpV6=true
&IPv6Address=drIbwOFr
&SubnetId=BvhMJWKe
&VPCId=OECssiom
&HighPerformance=true
```

### 响应示例
    
```json
{
  "Action": "CreateURedisGroupResponse",
  "GroupId": "uredis-00XXX",
  "RetCode": 0
}
```





