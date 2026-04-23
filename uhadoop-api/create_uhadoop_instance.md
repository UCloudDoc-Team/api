# 新建集群 - CreateUHadoopInstance

## 简介

新建一个uhadoop集群






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUHadoopInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUHadoopInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Password** | string | 集群机器的登录密码 |**Yes**|
| **FrameworkVersion** | string | 版本,例如：3.2.1-udh3.0,通过ListUHadoopFrameworkApp接口获取 |**Yes**|
| **InstanceGroupConfigs.N** | string | 节点配置，里面包括NodeType（机型），NodeRole（节点类别，值为其中之一：master\|core\|task），Count（数量），DataDiskType（数据盘类别），DataDiskSize（数据盘大小），DataDiskNum（数据盘数量），BootDiskType（系统盘类型），BootDiskSize（系统盘大小），通过GetUHadoopNodeType接口获取，示例为：<br />InstanceGroupConfigs.0.NodeType=o.hadoop2m.xlarge<br />InstanceGroupConfigs.0.NodeRole=master<br />InstanceGroupConfigs.0.Count=2<br />InstanceGroupConfigs.0.DataDiskType=CLOUD_RSSD<br />InstanceGroupConfigs.0.DataDiskSize=100<br />InstanceGroupConfigs.0.DataDiskNum=1<br />InstanceGroupConfigs.0.BootDiskType=CLOUD_RSSD<br />InstanceGroupConfigs.0.BootDiskSize=50<br />InstanceGroupConfigs.1.NodeType=o.hadoop2m.xlarge<br />InstanceGroupConfigs.1.NodeRole=core<br />InstanceGroupConfigs.1.Count=3<br />InstanceGroupConfigs.1.DataDiskType=CLOUD_RSSD<br />InstanceGroupConfigs.1.DataDiskSize=200<br />InstanceGroupConfigs.1.DataDiskNum=1<br />InstanceGroupConfigs.1.BootDiskType=CLOUD_RSSD<br />InstanceGroupConfigs.1.BootDiskSize=50 |**Yes**|
| **VPCId** | string | VPCId |**Yes**|
| **SubnetId** | string | 子网ID |**Yes**|
| **AppConfig.N** | string | 集群需要安装的组件，格式：组件#版本<br />通过ListUHadoopFrameworkApp接口获取，例如：Spark#3.3.0<br /> |**Yes**|
| **Framework** | string | 框架，值为'Hadoop'\|'HDFS'\|'MR'\|'StarRocks'之一,框架，例如Hadoop\|MR\|HDFS\|StarRocks Hadoop框架包含存储与计算服务 MR集群包含计算服务 HDFS只包含存储服务,StarRocks为StarRocks集群 |**Yes**|
| **ChargeType** | string | 支付类别，默认：Month |No|
| **Quantity** | int | 数量，默认1 |No|
| **BusinessId** | string | 工作组ID，默认Default |No|
| **StorgeClusterId** | string | Framework为‘MR’时，存储集群ID |No|
| **StandAloneMetaStore** | string | 目前只支持传‘udb’ |No|
| **IsSecurityEnabled** | string | 是否开启安全组 |No|
| **SecGroupIds** | string | 安全组ID，字符串数组，IsSecurityEnabled为true时生效 |No|
| **US3Bucket** | string | US3 bucket名称，仅支持框架为StarRocks存算分离时传入 |No|
| **US3AccessKey** | string | US3 配置公钥，仅支持框架为StarRocks存算分离时传入 |No|
| **US3SecretKey** | string | US3 配置私钥，仅支持框架为StarRocks存算分离时传入 |No|
| **US3TokenName** | string | US3 Token名称，仅支持框架为StarRocks存算分离时传入 |No|
| **InstanceName** | string | 实例名称，默认为实例ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceId** | string | 实例ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUHadoopInstance
&ClusterInstanceName=SCAZOhhf
&LoginMode=ClgBNXvF
&Password=DShVPErx
&UDDPFramework=tBqteOcF
&FrameworkVersion=PVKgDBmu
&Quantity=5
&ChargeType=SfKYKQEp
&SecurityGroupId=brvpDbmr
&Tag=OZlRuwXa
&StartScript=ZJCNlgKC
&UFile=BKtptDlx
&UFilePath=ZchvsBQs
&InstanceGroupConfigs.n=bDvnwfSF
&StorgeClusterId=WBFaOhBe
&StorgeClusterId=UNNcwWVM
&StandAloneMetaStore=tseScAOA
&IsSecGroup=snixnSRV
&SecGroupIds=SuSRyLCI
&US3Bucket=bJkkhHgq
&US3AccessKey=NNpkVgSM
&US3SecretKey=aLvFEmtp
&US3TokenName=eyJNObKK
&AppConfig.n=xSiBKqdu
&AppConfig.n=DKRIJHXG
```

### 响应示例
    
```json
{
  "Action": "CreateUHadoopInstanceResponse",
  "InstanceId": "PEqPVGfk",
  "Message": "ThrsaApT",
  "RetCode": 0
}
```





