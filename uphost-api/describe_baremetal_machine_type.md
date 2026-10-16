# 获取裸金属机型的详细信息 - DescribeBaremetalMachineType

## 简介

获取裸金属机型的详细描述信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeBaremetalMachineType)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeBaremetalMachineType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Type** | string | 具体机型。若不填写，则返回全部机型 |No|
| **APIVersion** | string | 请求版本。仅支持v2，不传或传其他值表示请求旧版本 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MachineTypes** | array[[*PHostCloudMachineTypeSetV2*](#PHostCloudMachineTypeSetV2)] | 机型列表，模型：PHostCloudMachineTypeSetV2,仅在入参Version=v2时返回 |No|

#### 数据模型


#### PHostCloudMachineTypeSetV2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 机型所在可用区 |**Yes**|
| **CPU** | [*PHostCPUSetV2*](#PHostCPUSetV2) | CPU信息 |**Yes**|
| **Disks** | array[[*PHostDiskSetV2*](#PHostDiskSetV2)] | 磁盘信息 |**Yes**|
| **Components** | array[[*PHostComponentSet*](#PHostComponentSet)] | 组件信息 |**Yes**|
| **Type** | string | 物理云主机机型别名 |**Yes**|
| **RaidSupported** | string | 是否支持做Raid。枚举值：可以：Yes；不可以：No |**Yes**|
| **Memory** | int | 内存大小，单位MB |**Yes**|
| **IsBaremetal** | boolean | 是否是裸金属机型 |No|
| **IsNew** | boolean | 是否需要加新机型标记 |No|
| **GpuInfo** | [*PHostGpuInfoV2*](#PHostGpuInfoV2) | GPU信息 |No|
| **OnSale** | boolean | 通常获取到的都是可售卖的 |No|
| **Stock** | int | 库存数量 |No|
| **StockStatus** | string | 库存状态。枚举值：有库存：Available；无库存：SoldOut |No|
| **Price** | object | 参考价格。字典类型，default:为默认价格；cn-wlcb-01:乌兰察布A可用区价格 |No|
| **Cluster** | string | 集群名。枚举值：千兆网络集群：1G；万兆网络集群：10G；智能网卡网络：25G； |No|
| **Scene** | array[string] | 适用场景。例如：ai表示AI学习场景； |No|
| **IsGpu** | boolean | 是否是GPU机型 |No|

#### PHostCPUSetV2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CoreCount** | int | CPU核数 |**Yes**|
| **Count** | int | CPU个数 |**Yes**|
| **Model** | string | CPU型号 |**Yes**|
| **Frequency** | string | CPU主频 |No|

#### PHostDiskSetV2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Space** | int | 空间大小 |**Yes**|
| **Name** | string | 磁盘名 |**Yes**|
| **IoCap** | int | IO性能 |No|
| **Number** | int | 数量 |No|
| **UnitSize** | int | 转换单位 |No|
| **RaidLevel** | int | Raid级别 |No|
| **DiskType** | int | 磁盘类型 |No|

#### PHostComponentSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 组件名称 |No|
| **Count** | int | 组件数量 |No|

#### PHostGpuInfoV2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | GPU名称，例如：NVIDIA_V100S |**Yes**|
| **Count** | int | GPU数量 |**Yes**|
| **Memory** | string | GPU显存大小 |**Yes**|
| **Performance** | string | GPU性能指标 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeBaremetalMachineType
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=DjVQZCeC
&Type=YOdfvZKs
&Version=degvdYhk
```

### 响应示例
    
```json
{
  "Action": "DescribeBaremetalMachineTypeResponse",
  "MachineTypes": [
    {}
  ],
  "RetCode": 0
}
```





