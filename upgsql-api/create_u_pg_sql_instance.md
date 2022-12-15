# 创建PG云数据库 - CreateUPgSQLInstance

## 简介

创建PG云数据库






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUPgSQLInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUPgSQLInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **DBVersion** | string | PostgreSQL的版本，pg10.4:postgresql-10.4，pg13.4:postgresql-13.4 |**Yes**|
| **ParamGroupID** | int | DB实例使用的配置参数组id |**Yes**|
| **AdminPassword** | string | 管理员密码 |**Yes**|
| **Port** | int | 端口默认为5432 |**Yes**|
| **DiskSpace** | string | 磁盘空间(GB) |**Yes**|
| **MachineType** | string | 机器配置类型，2核4G的机器:o.pgsql2m.medium |**Yes**|
| **SubnetID** | string | 子网ID |**Yes**|
| **VPCID** | string | VPC的ID |**Yes**|
| **InstanceMode** | string | UDB实例模式类型, 可选值如下: "Normal": 普通版UDB实例 "HA": 高可用版UDB实例 默认是"Normal" |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceID** | string | 资源ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUPgSQLInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=rRMHysZc
&Name=nyWogTGQ
&DBVersion=BwXYndWK
&ParamGroupID=9
&AdminPassword=ttiytaRC
&Port=1
&DiskSpace=wugxxeez
&MachineType=EtOtOWVL
&SubnetID=vYfdUNLf
&VPCID=JkndYJUI
&InstanceMode=YgRHGskR
```

### 响应示例
    
```json
{
  "Action": "CreateUPgSQLInstanceResponse",
  "InstanceID": "PKvSpnFx",
  "RetCode": 0
}
```





