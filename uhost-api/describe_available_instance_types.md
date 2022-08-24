# 获取某个地域下可售/售罄的所有机型信息 - DescribeAvailableInstanceTypes

## 简介

DescribeAvailableInstanceTypes






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeAvailableInstanceTypes)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeAvailableInstanceTypes`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。  |No|
| **MachineTypes.N** | string | 指定机型列表 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AvailableInstanceTypes** | array[[*AvailableInstanceTypes*](#AvailableInstanceTypes)] | AvailableInstanceTypes |**Yes**|
| **Status** | string | 当前区域是否可售 |No|

#### 数据模型


#### AvailableInstanceTypes

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区信息 |No|
| **Name** | string | 机型名称：快杰O型\|O 、快杰共享型\|OM 、快杰内存型\|OMEM 、 快杰PRO型\|OPRO、通用N型\|N、高主频C型\|C和GPU G型\|G等 |No|
| **Status** | string | 机型状态：可售\|Normal 、 公测\|Beta、售罄\|Soldout、隐藏\|Hidden |No|
| **CpuPlatforms** | [*CpuPlatforms*](#CpuPlatforms) | 支持的CPU平台，并且按照Intel、AMD和Ampere分类返回 |No|
| **Disks** | array[[*Disks*](#Disks)] | 磁盘信息。磁盘主要分类如下：云盘\|cloudDisk、普通本地盘\|normalLocalDisk和SSD本地盘\|ssdLocalDisk。<br /><br />其中云盘主要包含普通云盘\|CLOUD_NORMAL、SSD云盘\|CLOUD_SSD和RSSD云盘\|CLOUD_RSSD。普通本地盘只包含普通本地盘\|LOCAL_NORMAL一种。SSD本地盘只包含SSD本地盘\|LOCAL_SSD一种。<br /><br />MinimalSize为磁盘最小值，如果没有该字段，最小值取基础镜像Size值即可（linux为20G，windows为40G）。MaximalSize为磁盘最大值。<br /><br />InstantResize表示系统盘是否允许扩容，如果是本地盘，则不允许扩容，InstantResize为false。<br /><br />Features为磁盘可支持的服务：数据方舟\|DATAARK，快照服务\|SNAPSHOT，加密盘\|Encrypted。 |No|
| **MachineSizes** | array[[*MachineSizes*](#MachineSizes)] | GPU、CPU和内存信息。Gpu为GPU可支持的规格，Cpu和Memory分别为CPU和内存可支持的规格。如果非GPU机型，GPU为0。<br /><br />MinimalCpuPlatform代表含义这个CPU和内存规格只能在列出来的CPU平台支持。 |No|
| **Features** | array[[*Features*](#Features)] | 	<br />虚机可支持的特性。目前支持的特性网络增强\|NetCapability、热升级\|Hotplug。<br /><br />网络增强分为关闭\|Normal、网络增强1.0\|Super和网络增强2.0\|Ultra。<br /><br />Name为可支持的特性名称，Modes为可以提供的模式类别等，RelatedToImageFeature为镜像上支持这个特性的标签。例如DescribeImage返回的字段Features包含HotPlug，说明该镜像支持热升级。<br /><br />MinimalCpuPlatform表示这个特性必须是列出来的CPU平台及以上的CPU才支持。 |No|
| **MachineClass** | string | 区分是否是GPU机型：GPU机型\|GPU，非GPU机型\|Normal。 |No|
| **GraphicsMemory** | [*GraphicsMemory*](#GraphicsMemory) | GPU的显存指标，value为值，单位是GB。 |No|
| **Performance** | [*Performance*](#Performance) | GPU的性能指标，value为值，单位是TFlops。 |No|

#### CpuPlatforms

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Intel** | array[string] | 返回Intel的CPU平台信息，例如：Intel: ['Intel/CascadeLake','Intel/CascadelakeR','Intel/IceLake']<br /> |No|
| **Amd** | array[string] | 返回AMD的CPU平台信息，例如：AMD: ['Amd/Epyc2']<br /> |No|
| **Ampere** | array[string] | 返回Arm的CPU平台信息，例如：Ampere: ['Ampere/Altra'] |No|

#### Disks

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 磁盘介质类别信息，磁盘主要分类如下：云盘\|cloudDisk、普通本地盘\|normalLocalDisk和SSD本地盘\|ssdLocalDisk。  |No|
| **BootDisk** | array[[*BootDiskInfo*](#BootDiskInfo)] | 系统盘信息 |No|
| **DataDisk** | array[[*DataDiskInfo*](#DataDiskInfo)] | 数据盘信息 |No|

#### MachineSizes

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Gpu** | int | Gpu为GPU可支持的规格即GPU颗数，非GPU机型，Gpu为0 |No|
| **Collection** | array[[*Collection*](#Collection)] | CPU和内存可支持的规格 |No|

#### Features

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 可支持的特性名称。目前支持的特性网络增强\|NetCapability、热升级\|Hotplug |No|
| **Modes** | array[[*FeatureModes*](#FeatureModes)] | 可以提供的模式类别 |No|

#### GraphicsMemory

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Value** | int | 值，单位是GB |No|
| **Rate** | int | 交互展示参数，可忽略 |No|

#### Performance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Value** | float | 值，单位是TFlops |No|
| **Rate** | int | 交互展示参数，可忽略 |No|

#### FeatureModes

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 模式\|特性名称 |No|
| **RelatedToImageFeature** | array[string] | 为镜像上支持这个特性的标签。例如DescribeImage返回的字段Features包含HotPlug，说明该镜像支持热升级。 |No|
| **MinimalCpuPlatform** | array[string] | 这个特性必须是列出来的CPU平台及以上的CPU才支持 |No|

#### Collection

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Cpu** | int | CPU规格 |No|
| **Memory** | array[int] | 内存规格 |No|
| **MinimalCpuPlatform** | array[string] | CPU和内存规格只能在列出来的CPU平台支持 |No|

#### BootDiskInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 系统盘类别，包含普通云盘\|CLOUD_NORMAL、SSD云盘\|CLOUD_SSD和RSSD云盘\|CLOUD_RSSD。普通本地盘只包含普通本地盘\|LOCAL_NORMAL一种。SSD本地盘只包含SSD本地盘\|LOCAL_SSD一种。 |No|
| **InstantResize** | boolean | 系统盘是否允许扩容，如果是本地盘，则不允许扩容，InstantResize为false。 |No|
| **MaximalSize** | int | MaximalSize为磁盘最大值 |No|
| **Features** | array[string] | 磁盘可支持的服务 |No|

#### DataDiskInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MinimalSize** | int | 磁盘最小值，如果没有该字段，最小值取基础镜像Size值即可（linux为20G，windows为40G）。 |No|
| **Name** | string | 数据盘类别，包含普通云盘\|CLOUD_NORMAL、SSD云盘\|CLOUD_SSD和RSSD云盘\|CLOUD_RSSD。普通本地盘只包含普通本地盘\|LOCAL_NORMAL一种。SSD本地盘只包含SSD本地盘\|LOCAL_SSD一种。 |No|
| **MaximalSize** | int | MaximalSize为磁盘最大值 |No|
| **Features** | array[string] | 数据盘可支持的服务 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeAvailableInstanceTypes
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=qOkTGfWf
&MachineTypes.N=STscCopU
```

### 响应示例
    
```json
{
  "Action": "DescribeAvailableInstanceTypesResponse",
  "AvailableInstanceTypes": "sNSlnDFQ",
  "RetCode": 0,
  "Status": "UGBTxoLj"
}
```





