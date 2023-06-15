# 创建分片集群 - CreateUMongoDBShardedCluster

## 简介

创建一个Mongodb分片集群






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUMongoDBShardedCluster)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUMongoDBShardedCluster`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 副本集实例名称，至少6位 |**Yes**|
| **DBVersion** | string | 副本集的Mongodb的版本，例如MongoDB-3.6, MongoDB-4.2 |**Yes**|
| **AdminPassword** | string | 管理员密码 |**Yes**|
| **MongosNodeCount** | int | Mongos节点数量 |**Yes**|
| **ShardCount** | int | 分片数量 |**Yes**|
| **NodeCount** | int | 每个分片中节点数量 |**Yes**|
| **DiskSpace** | int | 数据节点磁盘空间(GB) |**Yes**|
| **MachineTypeId** | string | 数据节点机型配置 |**Yes**|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC的ID |No|
| **Tag** | string | 实例所在的业务组名称 |No|
| **ChargeType** | string | 付费方式：Year， Month， Dynamic，Trial，默认: Month |No|
| **Quantity** | int | 购买时长，默认值1 |No|
| **ListenPort** | int | mongo服务端口 |No|
| **TemplateId** | string | 参数配置模版id |No|
| **MongosMachineTypeId** | string | Mongos节点机型配置 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUMongoDBShardedCluster
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=nClnlbpK
&Name=ikqLkxcS
&DBVersion=UrsRvxjz
&AdminPassword=CJRsfuaP
&DiskSpace=pNcPQRQc
&MachineTypeId=XnzJIuTI
&NodeCount=2
&SubnetId=eoHMiTqA
&VPCId=MskapaWl
&Tag=DaJVCUSu
&ChargeType=Year
&Quantity=3
&MongosNodeCount=5
&ShardCount=9
&MongosDiskSpace=9
&MongosNodeCount=3
&ShardCount=4
&MongosDiskSpace=1
&ListenPort=6
&TemplateId=QqyhaTzZ
&MongosMachineTypeId=jSdeeQvn
```

### 响应示例
    
```json
{
  "Action": "CreateUMongoDBShardedClusterResponse",
  "RetCode": 0
}
```





