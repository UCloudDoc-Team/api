# 获取实例列表信息 - ListUKafkaInstance

## 简介

获取实例列表信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUKafkaInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUKafkaInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Limit** | string | 默认为60 |No|
| **Offset** | string | 默认为0 |No|
| **VPCId** | string | VPCId |No|
| **SubnetId** | string | SubnetId |No|
| **BusinessId** | string | 业务组 ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterSet** | [*ClusterSet*](#ClusterSet) | 实例信息 |**Yes**|
| **TotalCount** | string | 总数 |**Yes**|

#### 数据模型


#### ClusterSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ClusterInstanceId** | string | 实例id |No|
| **ClusterInstanceName** | string | 实例名称 |No|
| **Framework** | string | 框架 |No|
| **FrameworkVersion** | string | Kafka 框架版本 |No|
| **Remark** | string | 实例备注 |No|
| **CreateTime** | int | 实例创建时间戳 |No|
| **RunningTime** | int | 实例运行时间 |No|
| **ExpireTime** | int | 实例过期时间 |No|
| **AutoRenew** | string | 是否自动续费 |No|
| **ChargeType** | string | 付费类型 |No|
| **UHostCount** | int | 实例节点个数 |No|
| **RedundantCount** | int | 冗余计数（已废弃） |No|
| **State** | string | 实例当前状态,集群状态："Running"\| "Abnormal"\| "Creating"\| "Deleting"\| "CreateFailed"\| "DeleteFailed"\| "Unavailable"\| "Deleted"\| "Updating"\| "Deploying"\| "Migrating"\| "ExpandFailed" |No|
| **Tag** | string | 实例标记 |No|
| **InstanceGroupType** | string | 实例机型 |No|
| **VPCId** | string | 所属 VPC id |No|
| **SubnetId** | string | 所属子网 id |No|
| **BusinessId** | string | 业务组 ID  |No|
| **NewMessage** | string | 事件状态未读消息（已废弃） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUKafkaInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=lrthkcCU
&Limit=UrYjkKTm
&Offset=nORcPySS
&VPCId=ooZXMZYr
&SubnetId=aICLRzKS
&BusinessId=gdOiLduj
```

### 响应示例
    
暂无





