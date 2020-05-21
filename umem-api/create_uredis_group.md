# 创建主备redis - CreateURedisGroup

## 简介

创建主备redis






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateURedisGroup)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


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
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Name** | string | 请求创建组的名称 (范围[6-63],只能包含英文、数字以及符号-和_) |**Yes**|
| **HighAvailability** | string | 是否开启高可用,enable或disable |**Yes**|
| **Size** | int | 每个节点的内存大小,单位GB,默认1GB,目前仅支持1/2/4/8/16/32,六种 |No|
| **AutoBackup** | string | 是否自动备份,enable或disable，默认disable |No|
| **BackupTime** | int | 自动备份开始时间,范围[0-23],默认3点 |No|
| **ConfigId** | string | 配置ID,目前支持 3.0版本配置ID:"03f58ca9-b64d-4bdd-abc7-c6b9a46fd801",3.2版本配置ID:"3e45ac48-f8a2-a9q2-261d-l342dab130gf", 4.0版本配置ID:"6c9298a3-9d7f-428c-b1d0-e87ab3b8a1ea",默认版本3.0,从备份创建为必传项 |No|
| **Version** | string | Redis版本信息(详见DescribeURedisVersion返回结果),默认版本3.0 |No|
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
```

### 响应示例
    
```json
{
  "Action": "CreateURedisGroupResponse",
  "GroupId": "uredis-00XXX",
  "RetCode": 0
}
```





