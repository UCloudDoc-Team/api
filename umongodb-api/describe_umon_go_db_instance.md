# 描述MongoDB实例 - DescribeUMongoDBInstance

## 简介

描述MongoDB实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMongoDBInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMongoDBInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 实例资源ID |**Yes**|
| **ClusterType** | string | 集群类型，ReplicaSet：副本集，SharedCluster：分片集群 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterInfo** | [*ClusterInfo*](#ClusterInfo) | 副本集信息 |No|

#### 数据模型


#### ClusterInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **ZoneId** | int |  |No|
| **ClusterType** | string | 集群类型，ReplicaSet :副本集，SharedCluster：分片集 |No|
| **ClusterId** | string | 集群ID |No|
| **InstanceName** | string | 实例名称 |No|
| **State** | string | 副本集/分片集群状态标记 Initing：初始化中，InitFailed：安装失败，Starting：启动中，StartFailed：启动失败，Running：运行，Stopping：关闭中，Stopped：已关闭, StopFailed：关闭失败，Deleting：删除中，Deleted：已删除，DeleteFailed：删除失败，Restarting：重启中，RestartFailed：重启失败。 |No|
| **DBVersion** | string | 副本集的Mongodb的版本 |No|
| **DiskSpace** | int | 磁盘空间(GB), 默认根据配置机型 |No|
| **MachineTypeId** | string | 计算规格 |No|
| **CreateTime** | int | DB实例创建时间 |No|
| **ConfigReplicaInfo** | [*ReplicaInfo*](#ReplicaInfo) | ConfigSrv信息 |No|
| **DataReplicaInfos** | array[[*ReplicaInfo*](#ReplicaInfo)] | 数据副本信息  |No|
| **MongosInfo** | array[[*NodeInfo*](#NodeInfo)] | Mongos节点信息 |No|
| **ConnectURL** | string | 副本集的访问地址 |No|
| **DeleteTime** | int | DB实例删除时间 |No|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC的ID |No|
| **ShardCount** | int | 分片数量，分片集有效 |No|
| **ShardNodeCount** | int | 每分片节点数量，分片集有效 |No|
| **MongosCount** | int | Mongos节点数量，分片集有效 |No|
| **ConfigNodeCount** | int | Config配置集群节点数量，分片集有效 |No|
| **ConfigMachineType** | string | Config配置集群节点配置，分片集有效 |No|
| **Tag** | string | 实例业务组 |No|

#### ReplicaInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ReplicaId** | string | 副本集ID |No|
| **ClusterId** | string | 集群ID |No|
| **ReplicaType** | string | 副本类型,ConfigRepl或者DataRepl |No|
| **State** | string | 副本集/分片集群状态标记 Initing：初始化中，InitFailed：安装失败，Starting：启动中，StartFailed：启动失败，Running：运行，Stopping：关闭中，Stopped：已关闭, StopFailed：关闭失败，Deleting：删除中，Deleted：已删除，DeleteFailed：删除失败，Restarting：重启中，RestartFailed：重启失败。 |No|
| **MachineType** | string | 机器类型 |No|
| **MachineTypeId** | string | 机器类型Id |No|
| **IsolationGroupId** | string | 隔离组ID |No|
| **NodeInfos** | array[[*NodeInfo*](#NodeInfo)] | 副本集下的节点信息 |No|
| **NodeCount** | int | 副本集下的节点数量 |No|
| **CreateTime** | int | 副本集创建时间 |No|
| **DeleteTime** | int | 副本集删除时间 |No|
| **ModifyTime** | int | 副本集修改时间 |No|

#### NodeInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **ZoneId** | int | 可用区ID |No|
| **NodeId** | string | 节点ID |No|
| **NodeRole** | string | 节点角色，Primary/Secondary/Arbiter/Startup等等 |No|
| **NodeType** | string | 节点类型 |No|
| **State** | string | 副本集/分片集群状态标记 Initing：初始化中，InitFailed：安装失败，Starting：启动中，StartFailed：启动失败，Running：运行，Stopping：关闭中，Stopped：已关闭, StopFailed：关闭失败，Deleting：删除中，Deleted：已删除，DeleteFailed：删除失败，Restarting：重启中，RestartFailed：重启失败。 |No|
| **DBVersion** | string | 副本集的Mongodb的版本 |No|
| **ClusterId** | string | 节点所属副本集ID |No|
| **VirtualClusterId** | string | 虚拟节点ID |No|
| **MachineType** | string | 机型信息 |No|
| **MachineTypeId** | string | 机型信息ID |No|
| **CreateTime** | int | DB实例创建时间 |No|
| **DataDisk** | [*DiskInfo*](#DiskInfo) | 数据盘信息 |No|
| **SysDisk** | [*DiskInfo*](#DiskInfo) | 系统盘信息 |No|

#### DiskInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskId** | string | 磁盘id |No|
| **DiskSize** | int | 磁盘容量单位GB |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMongoDBInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=pismPnWj
&ClusterId=qhvujvIg
&ClusterType=Hxrfshbu
```

### 响应示例
    
```json
{
  "Action": "DescribeUMongoDBInstanceResponse",
  "ClusterInfo": {},
  "RetCode": 0
}
```





