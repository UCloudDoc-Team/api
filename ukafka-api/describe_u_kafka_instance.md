# 获取整个集群的信息-DescribeUKafkaInstance

获取整个集群的信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ClusterInstanceId|string|集群ID|**Yes**|
|Filter|string|是否过滤掉已删除节点，默认为‘true’|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ClusterSet|array|集群信息列表|**Yes**|

## ClusterInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|所属可用区|No|
|AppConfigCount|string|集群App 配置数量|No|
|AppConfigSet|array|集群App配置|No|
|BusinessId|string|business id|No|
|ChargeType|string|付费类型|No|
|ClusterInstanceId|string|集群id|No|
|ClusterInstanceName|string|集群名称|No|
|CreateTime|int|集群创建时间|No|
|DataSyncInfo|string|flume 数据同步信息|No|
|ExpireTime|string|集群过期时间|No|
|Framework|string|集群框架|No|
|FrameworkVersion|string|集群框架版本|No|
|NetworkId|string|网络 id|No|
|Remark|string|集群备注|No|
|RunningTime|string|集群运行时间|No|
|State|string|集群当前状态,集群状态："Running"| "Abnormal"| "Creating"| "Deleting"| "CreateFailed"| "DeleteFailed"| "Unavailable"| "Deleted"| "Updating"| "Deploying"| "Migrating"| "ExpandFailed"|No|
|SubnetId|string|所属子网 id|No|
|Tag|string|集群标记|No|
|UHostCount|string|集群节点个数|No|
|UHostSet|array|节点信息列表|No|
|VPCId|string|所属 VPC id|No|
|ValidBrokerNum|string|可用节点个数|No|

## Broker
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BrokerId|string|broker id|No|
|BrokerInfo|string|broker 关联topic 信息|No|
|CreateTime|string|broker 创建信息|No|
|DomainName|string|broker 域名|No|
|ExpireTime|int|broker 过期时间|No|
|IPSet|array|broker IP 信息|No|
|InstanceGroupType|string|broker 机型信息|No|
|KafkaPort|string|kafka 服务端口|No|
|Remark|string|broker 备注信息|No|
|ResourceId|string|broker 注册资源信息|No|
|SecurityGroupId|string|安全组 id|No|
|State|string|broker 当前状态|No|
|UHostConfig|object|broker 节点配置|No|
|UHostId|string|节点 id|No|
|UHostName|string|节点名称|No|
|UHostRole|string|节点类型|No|
|ZooKeeper|string|节点是否部署 zookeeper|No|
|ZooKeeperPort|string|zookeeper 服务端口|No|

## BrokerOfTopicInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|PartitionOnBroker|string|topic 在 broker 上分布的 partition 数量|No|
|Partitions|string|topic 在 broker上 partition 列表|No|
|Replication|int|Topic 副本数|No|
|TopicName|string|topic 名称|No|
|TotalPartitions|int|partition 数量|No|

## IP
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IP|string|IP地址|No|
|Type|string|IP类型|No|

## UHostConfig
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BootDiskSize|int|节点系统盘大小（单位G)|No|
|CPU|int|节点 CPU 核心数|No|
|DataDiskSize|int|节点数据盘大小（单位G)|No|
|Memory|int|节点内存(单位MB)|No|
|OS|string|节点内部系统名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUKafkaInstance
&Region=cn-zj
&Zone=cn-zj-01
&ClusterInstanceId=ukafka-wpdsk5
&Filter=true
```

# Response Example
```
{
    "Action": "DescribeUKafkaInstanceResponse", 
    "ClusterSet": [
        {
            "DataSyncInfo": {
                "Status": "Off"
            }, 
            "Zone": "cn-bj2-02", 
            "AppConfigCount": 0, 
            "State": "Running", 
            "ClusterInstanceId": "ukafka-wpdsk5", 
            "ValidBrokerNum": 4, 
            "VPCId": "uvnet-n10cep", 
            "Framework": "Kafka", 
            "SubnetId": "subnet-5ofcuz", 
            "UHostCount": 4, 
            "FrameworkVersion": "1.1.1", 
            "NetworkId": "", 
            "Remark": "", 
            "UHostSet": [
                {
                    "Remark": "", 
                    "SecurityGroupId": "", 
                    "ZooKeeperPort": 2181, 
                    "DomainName": "", 
                    "ZooKeeper": "Yes", 
                    "ResourceId": "kafkadocker-s2fpui", 
                    "KafkaPort": 9092, 
                    "InstanceGroupType": "J1-large", 
                    "UHostConfig": {
                        "BootDiskSize": 20, 
                        "DataDiskSize": 200, 
                        "OS": "Kafka", 
                        "CPU": 2, 
                        "Memory": 4096
                    }, 
                    "UHostName": "ukafka-wpdsk5-kafka1", 
                    "ExpireTime": 1546272000, 
                    "IPSet": [
                        {
                            "IP": "10.9.167.48", 
                            "Type": "Private"
                        }
                    ], 
                    "State": "Running", 
                    "UHostId": "node-jzahyy", 
                    "BrokerId": "1", 
                    "Zookeeper": "Yes", 
                    "BrokerInfo": [
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "foo", 
                            "PartitionOnBroker": "3"
                        }, 
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "bar", 
                            "PartitionOnBroker": "3"
                        }, 
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "nil", 
                            "PartitionOnBroker": "3"
                        }
                    ], 
                    "CreateTime": 1543299784, 
                    "UHostRole": "KafkaMaster"
                }, 
                {
                    "Remark": "", 
                    "SecurityGroupId": "", 
                    "ZooKeeperPort": 2181, 
                    "DomainName": "", 
                    "ZooKeeper": "Yes", 
                    "ResourceId": "kafkadocker-lhq3dv", 
                    "KafkaPort": 9092, 
                    "InstanceGroupType": "J1-large", 
                    "UHostConfig": {
                        "BootDiskSize": 20, 
                        "DataDiskSize": 200, 
                        "OS": "Kafka", 
                        "CPU": 2, 
                        "Memory": 4096
                    }, 
                    "UHostName": "ukafka-wpdsk5-kafka2", 
                    "ExpireTime": 1546272000, 
                    "IPSet": [
                        {
                            "IP": "10.9.83.108", 
                            "Type": "Private"
                        }
                    ], 
                    "State": "Running", 
                    "UHostId": "node-05znvw", 
                    "BrokerId": "2", 
                    "Zookeeper": "Yes", 
                    "BrokerInfo": [
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "foo", 
                            "PartitionOnBroker": "3"
                        }, 
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "bar", 
                            "PartitionOnBroker": "3"
                        }, 
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "nil", 
                            "PartitionOnBroker": "3"
                        }
                    ], 
                    "CreateTime": 1543299784, 
                    "UHostRole": "KafkaMaster"
                }, 
                {
                    "Remark": "", 
                    "SecurityGroupId": "", 
                    "ZooKeeperPort": 2181, 
                    "DomainName": "", 
                    "ZooKeeper": "Yes", 
                    "ResourceId": "kafkadocker-ithmgf", 
                    "KafkaPort": 9092, 
                    "InstanceGroupType": "J1-large", 
                    "UHostConfig": {
                        "BootDiskSize": 20, 
                        "DataDiskSize": 200, 
                        "OS": "Kafka", 
                        "CPU": 2, 
                        "Memory": 4096
                    }, 
                    "UHostName": "ukafka-wpdsk5-kafka3", 
                    "ExpireTime": 1546272000, 
                    "IPSet": [
                        {
                            "IP": "10.9.5.109", 
                            "Type": "Private"
                        }
                    ], 
                    "State": "Running", 
                    "UHostId": "node-0qqn0k", 
                    "BrokerId": "3", 
                    "Zookeeper": "Yes", 
                    "BrokerInfo": [
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "foo", 
                            "PartitionOnBroker": "3"
                        }, 
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "bar", 
                            "PartitionOnBroker": "3"
                        }, 
                        {
                            "Replication": 3, 
                            "Partitions": "0,1,2", 
                            "TotalPartitions": 3, 
                            "TopicName": "nil", 
                            "PartitionOnBroker": "3"
                        }
                    ], 
                    "CreateTime": 1543299784, 
                    "UHostRole": "KafkaMaster"
                }, 
                {
                    "Remark": "", 
                    "SecurityGroupId": "", 
                    "ZooKeeperPort": 2181, 
                    "DomainName": "", 
                    "ZooKeeper": "No", 
                    "ResourceId": "kafkadocker-bsvlbi", 
                    "KafkaPort": 9092, 
                    "InstanceGroupType": "J1-large", 
                    "UHostConfig": {
                        "BootDiskSize": 20, 
                        "DataDiskSize": 200, 
                        "OS": "Kafka", 
                        "CPU": 2, 
                        "Memory": 4096
                    }, 
                    "UHostName": "ukafka-wpdsk5-kafka4", 
                    "ExpireTime": 1546272000, 
                    "IPSet": [
                        {
                            "IP": "10.9.4.88", 
                            "Type": "Private"
                        }
                    ], 
                    "State": "Running", 
                    "UHostId": "node-scqtkk", 
                    "BrokerId": "4", 
                    "Zookeeper": "No", 
                    "BrokerInfo": [], 
                    "CreateTime": 1543814808, 
                    "UHostRole": "Kafka"
                }
            ], 
            "AppConfigSet": [], 
            "BusinessId": "", 
            "ClusterInstanceName": "barfoo", 
            "ExpireTime": 1546272000, 
            "RunningTime": 517495, 
            "Tag": "Default", 
            "ChargeType": "Month", 
            "CreateTime": 1543299784
        }
    ], 
    "RetCode": 0
}
```

