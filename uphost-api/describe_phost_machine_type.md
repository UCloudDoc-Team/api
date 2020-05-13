# 获取物理云机型信息 - DescribePHostMachineType

## 简介

获取物理云机型的详细描述信息





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribePHostMachineType)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribePHostMachineType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Type** | string | 具体机型。若不填写，则返回全部机型 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MachineTypes** | array[[*PHostMachineTypeSet*](#PHostMachineTypeSet)] | 机型列表，模型：PHostMachineTypeSet |**Yes**|

#### 数据模型


#### PHostMachineTypeSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 物理云主机机型别名，全网唯一。 |**Yes**|
| **Name** | string | 机型名 |No|
| **CPU** | [*PHostCPUSet*](#PHostCPUSet) | CPU信息 |No|
| **Memory** | int | 内存大小，单位GB |No|
| **Disks** | array[[*PHostDiskSet*](#PHostDiskSet)] | 磁盘信息 |No|
| **Components** | [*PHostComponentSet*](#PHostComponentSet) | 其他组件信息 |No|
| **Clusters** | array[[*PHostClusterSet*](#PHostClusterSet)] | 集群库存信息 |No|
| **RaidSupported** | string | 是否支持Raid。枚举值：支持：YES；不支持：NO |No|

#### PHostCPUSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Model** | string | CPU型号 |No|
| **Frequence** | float | CPU主频 |No|
| **Count** | int | CPU个数 |No|
| **CoreCount** | int | CPU核数 |No|

#### PHostDiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Space** | int | 单盘大小，单位GB |No|
| **Count** | int | 磁盘数量 |No|
| **Type** | string | 磁盘属性 |No|
| **Name** | string | 磁盘名称，sys/data |No|
| **IOCap** | int | 磁盘IO性能，单位MB/s（待废弃） |No|

#### PHostComponentSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 组件名称 |No|
| **Count** | string | 组件数量 |No|

#### PHostClusterSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 集群名。枚举值：千兆网络集群：1G；万兆网络集群：10G |No|
| **StockStatus** | string | 库存状态。枚举值：有库存：Available；无库存：SoldOut |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DecribePHostMachineType
&Region=cn-bj2
&Zone=cn-bj2-02
```

### 响应示例
    
```json
{
  "Action": "DescribePHostMachineTypeResponse",
  "MachineTypes": [
    {
      "CPU": {
        "CoreCount": 32,
        "Count": 2,
        "Frequence": "2.40",
        "Model": "Intel E5-2630 v3"
      },
      "Clusters": [
        {
          "Name": "10G",
          "StockStatus": "SoldOut"
        }
      ],
      "Components": {
        "Count": 0,
        "Name": ""
      },
      "Disks": [
        {
          "Count": 2,
          "IOCap": 1000,
          "Name": "sys",
          "Space": 1000,
          "Type": "SATA"
        },
        {
          "Count": 6,
          "IOCap": 1000,
          "Name": "data",
          "Space": 600,
          "Type": "SAS"
        }
      ],
      "Memory": 65536,
      "RaidSupported": "YES",
      "Type": "DB-2"
    }
  ],
  "RetCode": 0
}
```





