# 查询指定实例详细信息 - DescribeUESInstanceV2

## 简介

查询指定实例详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUESInstanceV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUESInstanceV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **InstanceId** | string | 集群实例ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | [*ClusterNodeV2Info*](#ClusterNodeV2Info) | 返回结果 |No|

#### 数据模型


#### ClusterNodeV2Info

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RequestId** | string |  |No|
| **ClusterInfo** | [*ClusterV2Info*](#ClusterV2Info) |  |No|
| **NodeInfoList** | array[[*NodeV2Info*](#NodeV2Info)] |  |No|

#### ClusterV2Info

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |No|
| **Zone** | string | 可用区 |No|
| **UESInstanceId** | string | 服务集群ID标识 |**Yes**|
| **UESInstanceName** | string | 服务集群名称 |**Yes**|
| **ServiceVersion** | string | 服务版本号 |**Yes**|
| **VPCId** | string | VPCID标识 |**Yes**|
| **State** | string | 服务集群状态 |**Yes**|
| **BusinessId** | string | 项目组ID标识 |No|
| **SubnetId** | string | 子网ID标识 |No|
| **Vip** | string | Vip |No|

#### NodeV2Info

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NodeId** | string | 节点ID |**Yes**|
| **NodeName** | string | 节点名称 |**Yes**|
| **NodeRole** | string | 节点类型 |**Yes**|
| **NodeIP** | string | 节点IP |**Yes**|
| **NodeConf** | string | 节点配置标识 |**Yes**|
| **NodeState** | string | 节点状态 |**Yes**|
| **DiskType** | string | 节点磁盘类型 |**Yes**|
| **DiskSize** | int | 节点磁盘大小 |**Yes**|
| **Memory** | int | 节点内存大小 |**Yes**|
| **CPU** | int | 节点cpu数量 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUESInstanceV2
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=wnuwqoNk
&InstanceId=jpcpqjYJ
```

### 响应示例
    
```json
{
  "Action": "DescribeUESInstanceV2Response",
  "Response": {},
  "RetCode": 0
}
```





