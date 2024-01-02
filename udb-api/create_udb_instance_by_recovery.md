# 将新建的db恢复到指定db某个指定时间点 - CreateUDBInstanceByRecovery

## 简介

创建db，将新创建的db恢复到指定db某个指定时间点






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDBInstanceByRecovery)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDBInstanceByRecovery`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **SrcDBId** | string | 源实例的Id |**Yes**|
| **RecoveryTime** | int | 恢复到某个时间点的时间戳(UTC时间格式，默认单位秒) |**Yes**|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Dynamic |No|
| **Quantity** | int | 购买时长，默认值1 |No|
| **UseSSD** | boolean | 指定是否是否使用SSD，默认使用主库的配置 |No|
| **UDBCId** | string | 专区的Id |No|
| **SubnetId** | string | 子网ID<br /> |No|
| **VPCId** | string | VPC的ID |No|
| **EnableIpV6** | boolean | 是否创建使用ipv6 资源， 默认为false， 或者不填， 创建ipv6为true |No|
| **Tables** | string | 指定需要恢复的表, 如果指定该字段则回档实例只有指定的表数据，格式为(库名.表名)， 指定多个用逗号隔开，eg: [ udb.test, mysql_school.my_student] |No|
| **AdminPassword** | string | 管理员密码 (指定库表回档到新实例时有效) |No|
| **SpecificationType** | string | 实例计算规格类型，0或不传代表使用内存方式购买，1代表使用内存-cpu可选配比方式购买，需要填写MachineType |No|
| **MachineType** | string | 规格类型ID,当SpecificationType为1时有效 |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DBId** | string | db实例id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDBInstanceByRecovery
&Region=cn-bj2
&ChargeType=Month   
&Name=udb-xxxxxxx
&SrcDBId=udb-xxxxx
&RecoveryTime=1432806384
&UseSSD=true
&SubnetId=SfBAwgaR
&VPCId=axmBjGuC
&EnableIpV6=true
&Tables=QLdHhoGF
&AdminPassword=CFJHxCUW
&AdminPassword=PFisJMZz
&AdminPassword=SPffecnI
&SpecificationType=yRERufjK
&MachineType=YWsemVcG
```

### 响应示例
    
```json
{
  "Action": "CreateUDBInstanceByRecoveryResponse",
  "DBId": "udb-xxxxx",
  "RetCode": 0
}
```





