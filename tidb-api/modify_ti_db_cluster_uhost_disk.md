# 变更集群节点磁盘容量 - ModifyTiDBClusterUhostDisk

## 简介

变更集群节点磁盘容量






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyTiDBClusterUhostDisk)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyTiDBClusterUhostDisk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Id** | string | 实例ID |**Yes**|
| **ScaleType** | string | 扩缩类型，枚举值为：SCALEOUT，扩容；SCALEIN，缩容； |**Yes**|
| **NodeConfig.ServerType** | string | 节点角色 |**Yes**|
| **NodeConfig.DiskSize** | int | 磁盘容量 |**Yes**|
| **StartTime** | int | 开始时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ServiceId** | string | 实例ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyTiDBClusterUhostDisk
&Region=cn-zj
&Id=pIFlYobP
&ScaleType=OxKZKKVR
&NodeConfig.ServerType=nzOvTpzB
&NodeConfig.DiskSize=1
&StartTime=5
```

### 响应示例
    
```json
{
  "Action": "ModifyTiDBClusterUhostDiskResponse",
  "RetCode": 0,
  "ServiceId": "TNbkUIEc"
}
```





