# 集群改配 - ResizeUClickhouseCluster

## 简介

集群改配






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ResizeUClickhouseCluster)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ResizeUClickhouseCluster`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群ID |**Yes**|
| **TargetMachineTypeId** | string | 目标机型ID，可通过GetUClickhouseClusterCreateOption接口获取具体值，与TargetDataDiskSize不能同时为空 |No|
| **TargetDataDiskSize** | int | 目标磁盘大小，单位GB，只能扩容，与TargetMachineTypeId不能同时为空 |No|
| **IsZooKeeperNode** | boolean | 是否为zookeeper节点，为true时表示升级zookeeper节点规格，为false时表示升级clickhouse节点规格，默认为false |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ResizeUClickhouseCluster
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=BJFkBKti
&ClusterId=VPkyXmCB
&TargetMachineTypeId=HOqLiWyU
&TargetDataDiskSize=6
&IsZooKeeperNode=false
```

### 响应示例
    
```json
{
  "Action": "ResizeUClickhouseClusterResponse",
  "Message": "oCPAaobG",
  "RetCode": 0
}
```





