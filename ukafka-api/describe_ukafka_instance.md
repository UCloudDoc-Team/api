# 获取整个集群的信息 - DescribeUKafkaInstance

## 简介

获取整个集群的信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUKafkaInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUKafkaInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ClusterInstanceId** | string | 集群ID |**Yes**|
| **Filter** | string | 是否过滤掉已删除节点，默认为‘true’ |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterSet** | array[[*ClusterInfo*](#ClusterInfo)] | 集群信息列表 |**Yes**|

#### 数据模型


#### ClusterInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 所属可用区 |No|
| **AppConfigCount** | string | 集群App 配置数量 |No|
| **AppConfigSet** | array[string] | 集群App配置 |No|
| **BusinessId** | string | business id |No|
| **ChargeType** | string | 付费类型 |No|
| **ClusterInstanceId** | string | 集群id |No|
| **ClusterInstanceName** | string | 集群名称 |No|
| **CreateTime** | int | 集群创建时间 |No|
| **DataSyncInfo** | string | flume 数据同步信息 |No|
| **ExpireTime** | string | 集群过期时间 |No|
| **Framework** | string | 集群框架 |No|
| **FrameworkVersion** | string | 集群框架版本 |No|
| **NetworkId** | string | 网络 id |No|
| **Remark** | string | 集群备注 |No|
| **RunningTime** | string | 集群运行时间 |No|
| **State** | string | 集群当前状态,集群状态："Running"\| "Abnormal"\| "Creating"\| "Deleting"\| "CreateFailed"\| "DeleteFailed"\| "Unavailable"\| "Deleted"\| "Updating"\| "Deploying"\| "Migrating"\| "ExpandFailed" |No|
| **SubnetId** | string | 所属子网 id |No|
| **Tag** | string | 集群标记 |No|
| **UHostCount** | string | 集群节点个数 |No|
| **UHostSet** | array[[*Broker*](#Broker)] | 节点信息列表 |No|
| **VPCId** | string | 所属 VPC id |No|
| **ValidBrokerNum** | string | 可用节点个数 |No|

#### Broker

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BrokerId** | string | broker id |No|
| **BrokerInfo** | string | broker 关联topic 信息 |No|
| **CreateTime** | string | broker 创建信息 |No|
| **DomainName** | string | broker 域名 |No|
| **ExpireTime** | int | broker 过期时间 |No|
| **IPSet** | array[[*IP*](#IP)] | broker IP 信息 |No|
| **InstanceGroupType** | string | broker 机型信息 |No|
| **KafkaPort** | string | kafka 服务端口 |No|
| **Remark** | string | broker 备注信息 |No|
| **ResourceId** | string | broker 注册资源信息 |No|
| **SecurityGroupId** | string | 安全组 id |No|
| **State** | string | broker 当前状态 |No|
| **UHostConfig** | [*UHostConfig*](#UHostConfig) | broker 节点配置 |No|
| **UHostId** | string | 节点 id |No|
| **UHostName** | string | 节点名称 |No|
| **UHostRole** | string | 节点类型 |No|
| **ZooKeeper** | string | 节点是否部署 zookeeper |No|
| **ZooKeeperPort** | string | zookeeper 服务端口 |No|

#### IP

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | IP地址 |No|
| **Type** | string | IP类型 |No|

#### UHostConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BootDiskSize** | int | 节点系统盘大小（单位G) |No|
| **CPU** | int | 节点 CPU 核心数 |No|
| **DataDiskSize** | int | 节点数据盘大小（单位G) |No|
| **Memory** | int | 节点内存(单位MB) |No|
| **OS** | string | 节点内部系统名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUKafkaInstance
&Region=cn-zj
&Zone=cn-zj-01
&ClusterInstanceId=ukafka-wpdsk5
&Filter=true
&Zone=cn-zj-01
```

### 响应示例
    
```json
{
  "Action": "DescribeUKafkaInstanceResponse",
  "ClusterSet": [
    {
      "AppConfigCount": 0,
      "AppConfigSet": [],
      "BusinessId": "",
      "ChargeType": "Month",
      "ClusterInstanceId": "ukafka-wpdsk5",
      "ClusterInstanceName": "barfoo",
      "CreateTime": 1543299784,
      "DataSyncInfo": {
        "Status": "Off"
      },
      "ExpireTime": 1546272000,
      "Framework": "Kafka",
      "FrameworkVersion": "1.1.1",
      "NetworkId": "",
      "Remark": "",
      "RunningTime": 517495,
      "State": "Running",
      "SubnetId": "subnet-5ofcuz",
      "Tag": "Default",
      "UHostCount": 4,
      "UHostSet": [
        {
          "BrokerId": "1",
          "BrokerInfo": [
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "foo",
              "TotalPartitions": 3
            },
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "bar",
              "TotalPartitions": 3
            },
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "nil",
              "TotalPartitions": 3
            }
          ],
          "CreateTime": 1543299784,
          "DomainName": "",
          "ExpireTime": 1546272000,
          "IPSet": [
            {
              "IP": "10.9.167.48",
              "Type": "Private"
            }
          ],
          "InstanceGroupType": "J1-large",
          "KafkaPort": 9092,
          "Remark": "",
          "ResourceId": "kafkadocker-s2fpui",
          "SecurityGroupId": "",
          "State": "Running",
          "UHostConfig": {
            "BootDiskSize": 20,
            "CPU": 2,
            "DataDiskSize": 200,
            "Memory": 4096,
            "OS": "Kafka"
          },
          "UHostId": "node-jzahyy",
          "UHostName": "ukafka-wpdsk5-kafka1",
          "UHostRole": "KafkaMaster",
          "ZooKeeper": "Yes",
          "ZooKeeperPort": 2181,
          "Zookeeper": "Yes"
        },
        {
          "BrokerId": "2",
          "BrokerInfo": [
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "foo",
              "TotalPartitions": 3
            },
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "bar",
              "TotalPartitions": 3
            },
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "nil",
              "TotalPartitions": 3
            }
          ],
          "CreateTime": 1543299784,
          "DomainName": "",
          "ExpireTime": 1546272000,
          "IPSet": [
            {
              "IP": "10.9.83.108",
              "Type": "Private"
            }
          ],
          "InstanceGroupType": "J1-large",
          "KafkaPort": 9092,
          "Remark": "",
          "ResourceId": "kafkadocker-lhq3dv",
          "SecurityGroupId": "",
          "State": "Running",
          "UHostConfig": {
            "BootDiskSize": 20,
            "CPU": 2,
            "DataDiskSize": 200,
            "Memory": 4096,
            "OS": "Kafka"
          },
          "UHostId": "node-05znvw",
          "UHostName": "ukafka-wpdsk5-kafka2",
          "UHostRole": "KafkaMaster",
          "ZooKeeper": "Yes",
          "ZooKeeperPort": 2181,
          "Zookeeper": "Yes"
        },
        {
          "BrokerId": "3",
          "BrokerInfo": [
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "foo",
              "TotalPartitions": 3
            },
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "bar",
              "TotalPartitions": 3
            },
            {
              "PartitionOnBroker": "3",
              "Partitions": "0,1,2",
              "Replication": 3,
              "TopicName": "nil",
              "TotalPartitions": 3
            }
          ],
          "CreateTime": 1543299784,
          "DomainName": "",
          "ExpireTime": 1546272000,
          "IPSet": [
            {
              "IP": "10.9.5.109",
              "Type": "Private"
            }
          ],
          "InstanceGroupType": "J1-large",
          "KafkaPort": 9092,
          "Remark": "",
          "ResourceId": "kafkadocker-ithmgf",
          "SecurityGroupId": "",
          "State": "Running",
          "UHostConfig": {
            "BootDiskSize": 20,
            "CPU": 2,
            "DataDiskSize": 200,
            "Memory": 4096,
            "OS": "Kafka"
          },
          "UHostId": "node-0qqn0k",
          "UHostName": "ukafka-wpdsk5-kafka3",
          "UHostRole": "KafkaMaster",
          "ZooKeeper": "Yes",
          "ZooKeeperPort": 2181,
          "Zookeeper": "Yes"
        },
        {
          "BrokerId": "4",
          "BrokerInfo": [],
          "CreateTime": 1543814808,
          "DomainName": "",
          "ExpireTime": 1546272000,
          "IPSet": [
            {
              "IP": "10.9.4.88",
              "Type": "Private"
            }
          ],
          "InstanceGroupType": "J1-large",
          "KafkaPort": 9092,
          "Remark": "",
          "ResourceId": "kafkadocker-bsvlbi",
          "SecurityGroupId": "",
          "State": "Running",
          "UHostConfig": {
            "BootDiskSize": 20,
            "CPU": 2,
            "DataDiskSize": 200,
            "Memory": 4096,
            "OS": "Kafka"
          },
          "UHostId": "node-scqtkk",
          "UHostName": "ukafka-wpdsk5-kafka4",
          "UHostRole": "Kafka",
          "ZooKeeper": "No",
          "ZooKeeperPort": 2181,
          "Zookeeper": "No"
        }
      ],
      "VPCId": "uvnet-n10cep",
      "ValidBrokerNum": 4,
      "Zone": "cn-bj2-02"
    }
  ],
  "RetCode": 0
}
```





