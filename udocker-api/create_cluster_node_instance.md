# 创建节点实例 - CreateClusterNodeInstance

## 简介

创建节点实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateClusterNodeInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateClusterNodeInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **ClusterId** | string | 集群Id |**Yes**|
| **SubnetId** | string | 子网Id |**Yes**|
| **CPU** | int | 虚拟CPU核数, 单位:个，范围：[1,16],最小值为1，其他值是2的倍数, 默认值: 4 |No|
| **Memory** | int | 内存大小, 单位: MB, 范围[2048, 65536], 步长: 2048, 默认值: 8192 |No|
| **DiskSpace** | int | 数据盘大小, 单位: GB, 范围[0,1000], 步长: 10, 默认值: 60 |No|
| **Name** | string | 节点实例名称, 默认:Node |No|
| **NetworkId** | string | 网络Id, 默认：创建基础网络主机 |No|
| **SecurityGroupId** | string | 防火墙Id, 默认：使用“Web服务器推荐”防火墙 |No|
| **ChargeType** | string | 计费类型  Year, Month, Dynamic， 默认:Month |No|
| **Quantity** | int | 购买时长，默认:1，单位是ChargeType中所选的单位 |No|
| **NodeType** | string | 主机类型  Normal：SSD: SSD机型) 默认：Normal，目前只支持Nornal |No|
| **VPCId** | string | VPCId |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeId** | string | 节点实例Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateClusterNodeInstance
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&ClusterId=cluster-xxx
&SubnetId=subnet-xxx
&CPU=4
&Memory=8192
&DiskSpace=60
&Name=node1
&ChargeType=Month
&Quantity=1
```

### 响应示例
    
```json
{
  "Action": "CreateClusterNodeInstanceResponse",
  "NodeId": "dnode-xxx",
  "RetCode": 0
}
```





