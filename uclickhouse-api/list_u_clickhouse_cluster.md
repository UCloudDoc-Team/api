# 获取UClickhouse集群列表 - ListUClickhouseCluster

## 简介

获取UClickhouse集群列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUClickhouseCluster)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUClickhouseCluster`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*ListUClickhouseClusterResponseData*](#ListUClickhouseClusterResponseData) | 返回数据 |**Yes**|

#### 数据模型


#### ListUClickhouseClusterResponseData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Clusters** | [*ClickhouseCluster*](#ClickhouseCluster) | 集群列表 |**Yes**|
| **TotalCount** | int | 集群总数 |**Yes**|

#### ClickhouseCluster

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClusterId** | string | 集群ID |**Yes**|
| **TopOrganizationId** | int | 公司ID |**Yes**|
| **OrganizationId** | int | 项目ID |**Yes**|
| **ClusterName** | string | 集群名称 |**Yes**|
| **VPCId** | string | VPCID |**Yes**|
| **SubnetId** | string | 子网ID |**Yes**|
| **ClickhouseVersion** | string | 集群版本 |**Yes**|
| **ZookeeperVersion** | string | Zookeeper版本 |**Yes**|
| **MachineType** | string | 机型 |**Yes**|
| **Status** | string | 集群状态：<br />CREATING（创建中）、<br />RUNNING（运行中）、<br />RESIZING（变配中）、<br />RESTARTING（重启中）、<br />UPGRADING（升级中）、<br />DESTROYING（销毁中）、<br />DESTROYED（已删除）、<br />CREATE_FAILED（创建失败）、<br />RESTART_FAILED（重启失败）、<br />DESTROY_FAILED（删除失败）、<br />RESIZE_FAILED（变配失败）、<br />BACKUP_RESTORING（备份恢复中）、<br />BACKUP_RESTORE_FAILED（备份恢复失败）、<br />EXPANDING（扩容中）、<br />EXPAND_FAILED（扩容失败） |**Yes**|
| **ShardCount** | int | 分片数 |**Yes**|
| **ReplicateCount** | int | 副本数 |**Yes**|
| **CreateTimestamp** | int | 集群创建时间 |**Yes**|
| **ClickhouseMachineTypeId** | string | Clickhouse机型ID |**Yes**|
| **ClickhouseMachineTypeName** | string | Clickhouse机型名称 |**Yes**|
| **RegionId** | int | 地域ID |**Yes**|
| **ZookeeperMachineTypeId** | string | Zookeeper机型ID |**Yes**|
| **ZookeeperMachineTypeName** | string | Zookeeper机型名称 |**Yes**|
| **ClickhouseDataDiskType** | string | Clickhouse数据盘类型 |**Yes**|
| **ClickhouseDataDiskSize** | int | Clickhouse数据盘大小 |**Yes**|
| **ZookeeperDataDiskType** | string | Zookeeper数据盘类型 |**Yes**|
| **ZookeeperDataDiskSize** | int | Zookeeper数据盘大小 |**Yes**|
| **ClickhouseNodeCPU** | int | Clickhouse节点CPU |**Yes**|
| **ClickhouseNodeMemory** | int | Clickhouse内存 |**Yes**|
| **ZookeeperNodeCPU** | int | Zookeeper节点CPU |**Yes**|
| **ZookeeperNodeMemory** | int | Zookeeper节点内存 |**Yes**|
| **IsZookeeperHA** | string | Zookeeper是否高可用 |**Yes**|
| **IsSecgroup** | string | 实例是否开启安全组 |**Yes**|
| **IsBackup** | string | 实例是否开启备份 |**Yes**|
| **IsTieredStorage** | string | 实例是否开启冷热分层 |**Yes**|
| **MultiZones** | array[string] | 实例所在可用区 |**Yes**|
| **ExpireTimestamp** | float | 实例过期时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUClickhouseCluster
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=iwYiVnQp
```

### 响应示例
    
```json
{
  "Action": "ListUClickhouseClusterResponse",
  "Data": {},
  "Message": "xGdMujex",
  "RetCode": 0
}
```





