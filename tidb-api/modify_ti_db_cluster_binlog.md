# 开启/关闭 binlog - ModifyTiDBClusterBinlog

## 简介

开启/关闭 binlog






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyTiDBClusterBinlog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyTiDBClusterBinlog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Id** | string | TIDB service id |**Yes**|
| **Enable** | string | binlog 状态 |**Yes**|
| **NodeConfig.ServerType** | string | 节点角色 |**Yes**|
| **NodeConfig.NodeCount** | int | 节点个数 |**Yes**|
| **NodeConfig.ConfigId** | string | 节点配置ID |**Yes**|
| **NodeConfig.DiskSize** | int | 节点磁盘大小 |**Yes**|

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
https://api.ucloud.cn/?Action=ModifyTiDBClusterBinlog
&Region=cn-zj
&Id=SvlosrOf
&Enable=MWYcvSmA
&ChargeType=fpnjoChg
&NodeConfig.ServerType=BpjBfHjL
&NodeConfig.NodeCount=1
&NodeConfig.ConfigId=CdzgGJYh
&NodeConfig.DiskSize=1
&OrderDetail.N.ProductName=kWizxlpV
&OrderDetail.N.Multiple=6
&CouponId=YzFEynMI
```

### 响应示例
    
```json
{
  "Action": "ModifyTiDBClusterBinlogResponse",
  "RetCode": 0,
  "ServiceId": "kMtBElcF"
}
```





