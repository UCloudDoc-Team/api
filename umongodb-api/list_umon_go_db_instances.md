# 获取副本集/分片集群列表 - ListUMongoDBInstances

## 简介

获取副本集/分片集群列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUMongoDBInstances)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUMongoDBInstances`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*MongodbInstance*](#MongodbInstance)] | 副本集ID |No|

#### 数据模型


#### MongodbInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |**Yes**|
| **ClusterId** | string | 副本集/分片集群ID |**Yes**|
| **Name** | string | 副本集/分片集群实例名称 |**Yes**|
| **DBVersion** | string | 副本集/分片集群的Mongodb的版本，包括MongoDB-3.6, MongoDB-4.2 |**Yes**|
| **ConnectURL** | string | 副本集/分片集群的访问地址 |**Yes**|
| **CreateTime** | int | 副本集/分片集群的创建时间 |**Yes**|
| **ClusterType** | string | 集群类型，ReplicaSet :副本集，SharedCluster：分片集 |**Yes**|
| **State** | string | 副本集/分片集群状态标记 Initing：初始化中，InitFailed：安装失败，Starting：启动中，StartFailed：启动失败，Running：运行，Stopping：关闭中，Stopped：已关闭, StopFailed：关闭失败，Deleting：删除中，Deleted：已删除，DeleteFailed：删除失败，Restarting：重启中，RestartFailed：重启失败,Upgrading: 升降级中，UpgradeFailed: 升降级失败,Switching:主备切换中 |**Yes**|
| **IPv6ConnectURL** | string | 副本集/分片集IPv6访问地址 |No|
| **ExpiredTime** | int | DB实例过期时间，采用UTC计时时间戳 |No|
| **DataComputeType** | [*MongodbMachineType*](#MongodbMachineType) | 数据节点计算规格 |No|
| **VPCId** | string | VPC的ID |No|
| **SubnetId** | string | 子网ID |No|
| **DiskSpace** | int | 数据节点磁盘空间(GB) |No|
| **Tag** | string | 业务组 |No|
| **CrossZones** | array[string] | 跨可用区列表 |No|

#### MongodbMachineType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MachineTypeId** | string | 机器类型ID o.mongo2m.medium，o.mongo2m.xlarge |**Yes**|
| **Description** | string | 配置简称  2C4G |**Yes**|
| **Cpu** | int | cpu核数 |**Yes**|
| **Memory** | int | 内存用量(GB) |**Yes**|
| **UHhostMachineType** | string | 机器类型，N/O |No|
| **Group** | string | 配置分组，2m , 4m |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUMongoDBInstances
&Region=cn-zj
&ProjectId=OEEeTdSt
&ClusterId=PYMePPwV
&ClusterId=RlOyJXoF
```

### 响应示例
    
```json
{
  "Action": "ListUMongoDBInstancesResponse",
  "ClusterId": "wWvPiKMh",
  "Message": "IToGkbMD",
  "RetCode": 0
}
```





