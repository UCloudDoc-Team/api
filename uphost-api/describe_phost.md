# 获取物理机信息 - DescribePHost

## 简介

获取物理机详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribePHost)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribePHost`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **PHostId.N** | string | PHost资源ID，若为空，则返回当前Region所有PHost。 |No|
| **Offset** | int | 数据偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20 |No|
| **UDiskIdForAttachment** | string | 要挂载的云盘id，过滤返回能被UDiskId挂载的云主机。目前主要针对rssd云盘使用 |No|
| **VPCId** | string | ULB使用参数，获取同VPC下机器信息。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的PHost总数 |No|
| **PHostSet** | array[[*PHostSet*](#PHostSet)] | PHost资源列表，参见 PHostSet |No|

#### 数据模型


#### PHostSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区，参见 [可用区列表](api/summary/regionlist) |No|
| **PHostId** | string | PHost资源ID |No|
| **SN** | string | 物理机序列号 |No|
| **PMStatus** | string | 物理云主机状态。枚举值：<br /><br /> > 初始化:Initializing; <br /><br /> > 启动中：Starting； <br /><br /> > 运行中：Running；<br /><br /> > 关机中：Stopping； <br /><br /> > 安装失败：InstallFailed； <br /><br /> > 重启中：Rebooting；<br /><br /> > 关机：Stopped； <br /><br /> > 迁移中(裸金属云盘)：Migrating |No|
| **Name** | string | 物理机名称 |No|
| **Remark** | string | 物理机备注 |No|
| **Tag** | string | 业务组 |No|
| **ImageName** | string | 镜像名称 |No|
| **OSname** | string | 操作系统名称 |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpireTime** | int | 到期时间 |No|
| **ChargeType** | string | 计费模式，枚举值为： Year，按年付费； Month，按月付费；默认为月付 |No|
| **PowerState** | string | 电源状态，on 或 off |No|
| **PHostType** | string | 物理机类型，参见DescribePHostMachineType返回值 |No|
| **Memory** | int | 内存大小，单位：MB |No|
| **CPUSet** | [*PHostCPUSet*](#PHostCPUSet) | CPU信息，见 PHostCPUSet |No|
| **DiskSet** | array[[*PHostDescDiskSet*](#PHostDescDiskSet)] | 磁盘信息，见 PHostDescDiskSet |No|
| **IPSet** | array[[*PHostIPSet*](#PHostIPSet)] | IP信息，见 PHostIPSet |No|
| **Cluster** | string | 网络环境。枚举值：千兆：1G ，万兆：10G |No|
| **AutoRenew** | string | 自动续费 |No|
| **IsSupportKVM** | string | 是否支持紧急登录 |No|
| **OSType** | string | 操作系统类型 |No|
| **Components** | string | 组件信息（暂不支持） |No|
| **RaidSupported** | string | 是否支持Raid。枚举值：Yes：支持；No：不支持。 |No|
| **PhostClass** | string | 物理云产品类型，枚举值：LocalDisk=>代表传统本地盘机型， CloudDisk=>云盘裸金属机型 |No|

#### PHostCPUSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Model** | string | CPU型号 |No|
| **Frequence** | float | CPU主频 |No|
| **Count** | int | CPU个数 |No|
| **CoreCount** | int | CPU核数 |No|

#### PHostDescDiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Space** | int | 单盘大小，单位GB |No|
| **Count** | int | 磁盘数量 |No|
| **Type** | string | 磁盘属性 |No|
| **Name** | string | 磁盘名称，sys/data |No|
| **IOCap** | int | 磁盘IO性能，单位MB/s（待废弃） |No|
| **Drive** | string | 裸金属机型参数：磁盘盘符 |No|
| **DiskId** | string | 裸金属机型参数：磁盘ID |No|
| **IsBoot** | string | 裸金属机型参数：是否是启动盘。True/False |No|

#### PHostIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OperatorName** | string |  国际: Internation， BGP: BGP， 内网: Private  |No|
| **IPId** | string | IP资源ID(内网IP无资源ID)（待废弃） |No|
| **IPAddr** | string | IP地址， |No|
| **MACAddr** | string | MAC地址 |No|
| **Bandwidth** | int | IP对应带宽，单位Mb，内网IP不显示带宽信息 |No|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribePHost
&Region=jpfMKyfI
&Zone=vdTrBzdz
&ProjectId=edaZIUNR
&PHostId.n=wdKzhBfK
&Offset=2
&Limit=9
&UDiskIdForAttachment=XmuOwhco
&VPCId=xnyTdDlO
```

### 响应示例
    
```json
{
  "Action": "DescribePHostResponse",
  "PHostSet": [
    {
      "AutoRenew": "vElhSowt",
      "CPUSet": {},
      "ChargeType": "HOJWsIek",
      "Cluster": "SvWpSdGG",
      "Components": "NHahHEJf",
      "CreateTime": 9,
      "DiskSet": [
        {
          "Count": 2,
          "DiskId": "PVQamRGq",
          "Drive": "iIFxawYp",
          "IOCap": 2,
          "IsBoot": "IAZXBkLX",
          "Name": "YQkYorHg",
          "Space": 5,
          "Type": "hLDhTxqn"
        }
      ],
      "ExpireTime": 5,
      "IPSet": [
        {
          "Bandwidth": 3,
          "IPAddr": "qCusNtNv",
          "IPId": "LwjcdFGT",
          "MACAddr": "PSlpiPlG",
          "OperatorName": "gUOcEZye",
          "SubnetId": "ixWBJCUq",
          "VPCId": "zwqAPBrO"
        }
      ],
      "ImageName": "gUYdJqug",
      "IsSupportKVM": "KqCCSXRY",
      "Memory": 7,
      "Name": "FozvyzAs",
      "OSType": "sEcEUJdn",
      "OSname": "oUGwtCWs",
      "PHostId": "tGnqGyiM",
      "PHostType": "JhbxVSaA",
      "PMStatus": "HJDlIYWi",
      "PhostClass": "hPSEhtat",
      "PowerState": "cBAaaIxY",
      "RaidSupported": "GgiMyJLC",
      "Remark": "etGTUBlU",
      "SN": "zPIhEFwm",
      "Tag": "HLukoXZc",
      "Zone": "zubgQpUw"
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





