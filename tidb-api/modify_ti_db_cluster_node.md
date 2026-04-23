# 集群扩缩容 - ModifyTiDBClusterNode

## 简介

集群扩缩容






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyTiDBClusterNode)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyTiDBClusterNode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Id** | string | TIDB service id |**Yes**|
| **ScaleType** | string | 扩缩类型，枚举值为：SCALEOUT，扩容；SCALEIN，缩容； |**Yes**|
| **NodeConfig.ServerType** | string | 节点角色 |**Yes**|
| **NodeConfig.NodeCount** | int | 节点个数 |**Yes**|
| **NodeConfig.ConfigId** | string | 节点配置ID |**Yes**|
| **ServerId** | string | 缩容节点ID，缩容时必填 |No|
| **StartTime** | int | 开始时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ServiceId** | string | ServiceId |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyTiDBClusterNode
&Region=cn-zj
&Id=gzTTgazj
&Enable=izoLTLdt
&ChargeType=oxITlFnh
&NodeConfig.ServerType=OmlCnMmu
&NodeConfig.NodeCount=4
&NodeConfig.ConfigId=kAzRcRzi
&NodeConfig.DiskSize=2
&OrderDetail.N.ProductName=MEAnyECJ
&OrderDetail.N.Multiple=4
&CouponId=DQMpkgdf
&ServerId=zRaYxfTI
&StartTime=6
```

### 响应示例
    
```json
{
  "Action": "ModifyTiDBClusterNodeResponse",
  "RetCode": 0,
  "ServiceId": "ImtDqQjf"
}
```





