# 获取云硬盘升级价格 - DescribeUDiskUpgradePrice

## 简介

获取UDisk升级价格信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDiskUpgradePrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDiskUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Size** | int | 购买UDisk大小,单位:GB,普通数据盘：范围[1\~8000]；SSD数据盘：范围[1\~8000]；普通系统盘：范围[1\~8000]；SSD系统盘：范围[1\~4000]；RSSD数据盘：范围[1\~32000]。 |**Yes**|
| **SourceId** | string | 升级目标UDisk ID |**Yes**|
| **UDataArkMode** | string | 【即将废弃，开启快照服务时，免费开启数据方舟】是否开启数据方舟。Yes：开启，No：不开启，默认值：No |No|
| **SnapshotService** | string | 	<br />是否开启快照服务。Yes：开启，No：不开启，默认值：No |No|
| **DiskType** | string | UDisk 类型: DataDisk（普通数据盘），SSDDataDisk（SSD数据盘），SystemDisk（普通系统盘），SSDSystemDisk（SSD系统盘），RSSDDataDisk（RSSD数据盘），默认值（DataDisk） |No|
| **MachineType** | string | 云主机机型（V2.0），枚举值["N", "C", "G", "O", "OM"]。参考[云主机机型说明](api/uhost-api/uhost_type)。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | int | 价格 |No|
| **OriginalPrice** | int | 用户折后价 (对应计费CustomPrice) |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/udisk/?Action=DescribeUDiskUpgradePrice
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=1   
&SourceId=bsm-xxx
&UDataArkMode =Yes
&DiskType = DataDisk
&MachineType=bSHaETUa
&SnapshotService=pYhGDMfE
```

### 响应示例
    
```json
{
  "Action": "DescribeUDiskUpgradePriceResponse",
  "CustomPrice": 7,
  "Price": 222,
  "RetCode": 0
}
```





