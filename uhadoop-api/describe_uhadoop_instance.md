# 描述集群 - DescribeUHadoopInstance

## 简介

描述集群






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUHadoopInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUHadoopInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **InstanceId** | string | 实例ID |**Yes**|
| **VPCId** | string | VPCID |No|
| **SubnetId** | string | 子网ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterSet** | array[[*ClusterInfo*](#ClusterInfo)] | 集群信息 |No|

#### 数据模型


#### ClusterInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |**Yes**|
| **Tag** | string | 集群Tag |**Yes**|
| **InstanceId** | string | 实例ID |**Yes**|
| **InstanceName** | string | 实例名称 |**Yes**|
| **Framework** | string | 框架，值为'Hadoop'\|'HDFS'\|'MR'\|'StarRocks'之一,框架，例如Hadoop\|MR\|HDFS\|StarRocks Hadoop框架包含存储与计算服务 MR集群包含计算服务 HDFS只包含存储服务,StarRocks为StarRocks集群 |**Yes**|
| **VPCId** | string | VPC ID |**Yes**|
| **SubnetId** | string | 子网ID |**Yes**|
| **BusinessId** | string | 业务组ID |**Yes**|
| **ReleaseVersion** | string | Uhadoop版本，值为 uhadoop 3.0\|uhadoop 2.2\|uhadoop 3.1 |**Yes**|
| **HadoopVersion** | string | Hadoop版本，值为 hadoop3.2.1-udh3.0\|hadoop3.3.4-udh3.1<br />\|hadoop2.8.5-udh2.2 |**Yes**|
| **CreateTime** | string | 创建时间 |**Yes**|
| **ChargeType** | string | 付费类型 |**Yes**|
| **ExpireTime** | string | 到期时间 |**Yes**|
| **State** | string | 状态，值为以下其中之一，Running(运行中)\|Creating(创建中)\|CreateFailed(创建失败)\|Deploying(部署中)\|Updating(变更中) |**Yes**|
| **MasterCount** | string | Master节点数量 |**Yes**|
| **CoreCount** | string | core节点数量 |**Yes**|
| **TaskCount** | string | Task节点数量 |**Yes**|
| **RunningTime** | string | 运行时间 |No|
| **AppConfigSet** | array[[*AppConfig*](#AppConfig)] | 组件集合 |No|
| **AppConfigCount** | string | 组件数量 |No|
| **IsOpenSecGroup** | string | 是否开启安全组 |No|
| **NodeSet** | array[[*NodeDetail*](#NodeDetail)] | 节点集合 |No|
| **NodeCount** | string | 节点数量 |No|
| **DataDiskKmsKeyId** | string | 集群磁盘加密密钥ID |No|

#### AppConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppName** | string | 需要安装的应用如：Hive,HBase, Spark,Hue,Pig等其他组件 |No|
| **AppVersion** | string | 应用的版本号(0.13.1,0.98.6 等等) |No|
| **AppStatus** | string | 应用的状态(运行中)'Running'｜(已停止)'Stopped'｜(启动中)'Starting'｜(停止中)'Stopping'\|(启动失败)'StartFailed'\|(停止失败)'StopFailed'\|(安装中)'Installing'\|(安装失败)'InstallFailed'\|(未安装)'NotInstalled',    <br /> |No|

#### NodeDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NodeId** | string | 节点ID |**Yes**|
| **HostType** | string | 机型种类，可选OutStanding(快杰机型)\|Genenal(普通机型)\|BareMetal(裸金属机型)三种类型 |**Yes**|
| **DiskSet** | array[[*DiskInfo*](#DiskInfo)] | 磁盘信息集合 |**Yes**|
| **CPU** | int | CPU数量 |**Yes**|
| **ResourceId** | string | 资源ID |**Yes**|
| **InstanceId** | string | 实例ID |**Yes**|
| **CreateTime** | int | 创建时间戳 |**Yes**|
| **IsNewType** | boolean | 是否是新机型,快杰机型，GPU机型，云盘裸金属机型为新机型 |**Yes**|
| **Memory** | int | 内存大小，单位为MB |**Yes**|
| **NodeRole** | string | 节点在集群中的⻆色(有Master,Core,Task 3种) |**Yes**|
| **NodeName** | string | 节点名称 |**Yes**|
| **Remark** | string | 备注 |**Yes**|
| **ExpireTime** | int | 节点的到期时间(下次扣款时间) |**Yes**|
| **NodeType** | string | 机型 |**Yes**|
| **FirewallGroupConfig** | array[[*SecurityGroupConfig*](#SecurityGroupConfig)] | 防火墙 信息 |**Yes**|
| **State** | string | 运行：Running； 创建中：Creating； 删除中：Deleting； 创建失败：CreateFailed； 不可用：Unavailable； 删除失败：DeleteFailed； 已删除：Deleted； 部署中： Deploying |**Yes**|
| **IPSet** | array[[*IPSet*](#IPSet)] | IP 信息 |**Yes**|
| **Scaling** | boolean | 是否是弹性伸缩节点 |No|

#### DiskInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskNum** | int | 磁盘数量 |**Yes**|
| **DiskRole** | string | 磁盘角色，一般分Boot和Data两种 |**Yes**|
| **DiskSize** | int | 磁盘大小，单位为GB |**Yes**|
| **DiskType** | string | 磁盘类型，分为CLOUD_RSSD(云盘RSSD)、CLOUD_SSD(云盘SSD)、LOCAL_SSD（本地SSD盘）、LOCAL_NORMAL（本地普通盘）、SATA（SATA盘） |**Yes**|

#### SecurityGroupConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GroupId** | string | 防火墙ID |**Yes**|
| **GroupName** | string | 防火墙组的名称 |**Yes**|
| **CreateTime** | int | 放火墙组创建时间，格式为Unix Timestamp |**Yes**|
| **Type** | string | 防火墙组类型，枚举值为： 0：用户自定义防火墙； 1：默认 Web防火墙； 2：默认非Web防火墙 |**Yes**|

#### IPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 类别 |No|
| **IP** | string | IP |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUHadoopInstance
&Region=TXuPYHyQ
&ProjectId=NHeVJnrG
&Zone=KtexcPsr
&InstanceId=CYvGuUJb
&VPCId=itgHxAiU
&SubnetId=RiNKnbPQ
```

### 响应示例
    
```json
{
  "Action": "DescribeUHadoopInstanceResponse",
  "ClusterSet": [
    {
      "AppConfigCount": 1,
      "AppConfigSet": [
        "ghlwKuyH"
      ],
      "BusinessId": "svtKHVNH",
      "ChargeType": "XbvAecgA",
      "ClusterInstanceId": "LkVLPTaH",
      "ClusterInstanceName": "kGUqVuvp",
      "CoreCount": 9,
      "CreateTime": 7,
      "ExpireTime": 5,
      "FrameworkVersion": "WxJiTlIz",
      "MasterCount": 6,
      "NetworkId": "mSJoXIrV",
      "RedundantCount": "qUhFHNOj",
      "Remark": "CMisvbBF",
      "RunningTime": "QsmhrbuJ",
      "StartScript": "hZlvwNmr",
      "State": "WwuAMaby",
      "SubnetId": "mWcCEvwo",
      "Tag": "GHSFvGXN",
      "TaskCount": "BKCkfBIb",
      "UDDPFramework": "ZMqFtSvc",
      "UFileState": "FxOSKEwU",
      "UHostCount": 2,
      "UHostSet": [
        {
          "CPU": 6,
          "CreateTime": 6,
          "DiskSet": [
            {
              "DiskNum": 3,
              "DiskRole": "xsoTuAKc",
              "DiskSize": 4,
              "DiskType": "hOQcIKfi"
            }
          ],
          "ExpireTime": 7,
          "FirewallGroupConfig": [
            {
              "CreateTime": 1,
              "GroupId": "buGmpRIR",
              "GroupName": "TpbFRmoV",
              "Type": "CYUaqnDD"
            }
          ],
          "HostType": "eNqsLpGM",
          "IPSet": [
            {
              "IP": "LxbDauMQ",
              "Type": "fKDcVkoX"
            }
          ],
          "InstanceId": "vAdeIoji",
          "IsNewType": true,
          "Memory": 3,
          "NodeId": "kHzICeJF",
          "NodeName": "QPJyCyau",
          "NodeRole": "TOhHvKuO",
          "NodeType": "LhNfhLqU",
          "Remark": "QejYhqCT",
          "ResourceId": "yrdUhyqZ",
          "State": "SJDXcPXC"
        }
      ]
    }
  ],
  "Message": "EQdOncZu",
  "RetCode": 0
}
```





