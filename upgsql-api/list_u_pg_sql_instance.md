# 获取云数据库列表 - ListUPgSQLInstance

## 简介

获取PG云数据库列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUPgSQLInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUPgSQLInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDBInstanceSet*](#UDBInstanceSet)] | 数据库信息列表 |**Yes**|

#### 数据模型


#### UDBInstanceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **InstanceID** | string | 资源ID |No|
| **Name** | string | 实例名称 |No|
| **DBVersion** | string | 实例的版本，包括postgresql-10.4,postgresql-13.4   |No|
| **InstanceMode** | string | normal/ha/readonly,普通/高可用/只读从库 |No|
| **State** | string | 实例状态标记 Initing：初始化中，InitFailed：安装失败，Starting：启动中， Running：运行，Stopping：关闭中，Stopped：已关闭,Deleted: 已删除，Upgrading: 升级中 ，Promoting：提升为主库进行中，Recovering：恢复中，RecoverFailed：恢复失败，StartFailed：启动失败，ShutdownFailed：关闭失败，Deleting：删除中，DeleteFailed：删除失败 |No|
| **MachineType** | string | 机器规格，格式为nCmG,n代表cpu核数，m代表内存大小(GB) |No|
| **VPCID** | string | VPC的ID |No|
| **SubnetID** | string | 子网ID |No|
| **CreateTime** | int | DB实例创建时间，采用UTC计时时间戳 |No|
| **ExpiredTime** | int | DB实例过期时间，采用UTC计时时间戳 |No|
| **IP** | string | DB实例ip |No|
| **Remark** | string | 备注 |No|
| **DataSet** | array[[*UDBReadonlyInstance*](#UDBReadonlyInstance)] | 从库列表 |No|

#### UDBReadonlyInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **InstanceID** | string | 资源ID |No|
| **Name** | string | 实例名称 |No|
| **DBVersion** | string | 实例的版本，包括postgresql-10.4,postgresql-13.4 |No|
| **InstanceMode** | string | normal/ha/readonly,普通/高可用/只读从库 |No|
| **State** | string | 实例状态标记 Initing：初始化中，InitFailed：安装失败，Starting：启动中， Running：运行，Stopping：关闭中，Stopped：已关闭,Deleted: 已删除，Upgrading: 升级中 ，Promoting：提升为主库进行中，Recovering：恢复中，RecoverFailed：恢复失败，StartFailed：启动失败，ShutdownFailed：关闭失败，Deleting：删除中，DeleteFailed：删除失败 |No|
| **MachineType** | string | 机器规格，格式为nCmG,n代表cpu核数，m代表内存大小(GB) |No|
| **VPCID** | string | VPC的ID |No|
| **SubnetID** | string | 子网ID |No|
| **CreateTime** | int | DB实例创建时间，采用UTC计时时间戳 |No|
| **ExpiredTime** | int | DB实例过期时间，采用UTC计时时间戳 |No|
| **IP** | string | DB实例ip |No|
| **Remark** | string | 备注 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUPgSQLInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=xQTrvEtW
```

### 响应示例
    
```json
{
  "Action": "ListUPgSQLInstanceResponse",
  "DataSet": [
    {
      "CreateTime": "LQiIDcUC",
      "DBVersion": "eSmGfTtw",
      "ExpiredTime": "QivusIMX",
      "IP": "jTZqgTRr",
      "InstanceID": "bPLlxURz",
      "InstanceMode": "hedJgcaN",
      "MachineType": "yuBcEIfJ",
      "Name": "dXrXuFJC",
      "State": "oTYEroYw",
      "SubnetID": "wohfomIJ",
      "VPCID": "bfgZFuLa",
      "Zone": "OYUfGKLT"
    }
  ],
  "Message": "nngXwSig",
  "RetCode": 0
}
```





