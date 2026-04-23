# 给集群添加节点 - AddUHadoopInstanceNode

## 简介

给已有集群添加一定数量的节点






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddUHadoopInstanceNode)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUHadoopInstanceNode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **NodeRole** | string | 节点的角色，值为task\|core\|client之一 |**Yes**|
| **NodeType** | string | 机型，如：o.hadoop2m.medium，<br />可从GetUHadoopNodeType接口获取 |**Yes**|
| **InstanceId** | string | 实例ID |**Yes**|
| **DataDiskNum** | string | 数据盘数量，非裸金属机型时必填 |No|
| **Password** | string | 密码,NodeRole为client时必填 |No|
| **BootDiskSize** | string | 系统盘容量,非裸金属机型必填 |No|
| **BootDiskType** | string | 系统盘类型，非裸金属机型必填，例如：CLOUD_RSSD |No|
| **DataDiskSize** | string | 数据盘容量，非裸金属机型必填 |No|
| **DataDiskType** | string | 数据盘类型，非裸金属机型必填，例如：CLOUD_RSSD |No|
| **NodeCount** | int | 节点数量,默认为1 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUHadoopInstanceNode
&ClusterInstanceId=BMZswchw
&InstanceGroupRole=Core
&LoginMode=Password
&Password=quSNyFJi
&ChargeType=WVTIhZXv
&UHostCount=9
&InstanceGroupType=xoFYEGnA
&BootDiskSize=YktrsZUl
&BootDiskType=PzYHCjXD
&DataDiskSize=TZCjfsjN
&DataDiskType=qoMxZDqz
&DataDiskNum=tQFbJpPG
&BootDiskSize=yfTVaTWl
&BootDiskType=pIwNGHWx
&DataDiskSize=NbVOzUhe
&DataDiskType=UnZzdJcw
&DataDiskNum=DZRIauiM
&Zone=pYnaZGBu
&Zone=tpIqFCwW
```

### 响应示例
    
```json
{
  "Action": "AddUHadoopInstanceNodeResponse",
  "Message": "oZruwVHW",
  "RetCode": 0
}
```





