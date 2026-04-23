# 列出用户所有的集群 - ListUHadoopInstance

## 简介

列出用户所有的uhadoop集群






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUHadoopInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUHadoopInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Limit** | int | 获取列表的长度限制，默认值为60 |No|
| **Offset** | int | 获取列表的偏移，默认值为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterSet** | array[[*ListClusterInfo*](#ListClusterInfo)] | 集群信息集合 |**Yes**|
| **TotalCount** | int | 总数 |**Yes**|

#### 数据模型


#### ListClusterInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |**Yes**|
| **InstanceId** | string | 实例ID |**Yes**|
| **InstanceName** | string | 实例名称 |**Yes**|
| **Framework** | string | 框架，值为'Hadoop'\|'HDFS'\|'MR'\|'StarRocks'之一，Hadoop框架包含存储与计算服务，MR集群包含计算服务，HDFS只包含存储服务，StarRocks为StarRocks集群 |**Yes**|
| **VPCId** | string | VPC ID |**Yes**|
| **SubnetId** | string | 子网ID |**Yes**|
| **BusinessId** | string | 业务组ID |**Yes**|
| **ReleaseVersion** | string | 	<br />Uhadoop版本，值为 uhadoop 3.0\|uhadoop 2.2\|uhadoop 3.1 |**Yes**|
| **HadoopVersion** | string | Hadoop版本，值为 hadoop3.2.1-udh3.0\|hadoop3.3.4-udh3.1 \|hadoop2.8.5-udh2.2 |**Yes**|
| **CreateTime** | string | 创建时间 |**Yes**|
| **State** | string | 状态，值为以下其中之一，Running(运行中)\|Creating(创建中)\|CreateFailed(创建失败)\|Deploying(部署中)\|Updating(变更中) |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUHadoopInstance
&Region=aWqKLPuu
&Zone=RzZPKPOd
&Filter=NTwPWPYB
&Limit=9
&Offset=5
```

### 响应示例
    
```json
{
  "Action": "ListUHadoopInstanceResponse",
  "ClusterSet": [
    "wjQSjXla",
    "rojtDqUM",
    "PQGNFoJv"
  ],
  "Message": "krqWNdLM",
  "RetCode": 0,
  "TotalCount": 1
}
```





