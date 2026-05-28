# 获取实例规格族列表（所有机型的信息） - DescribeHostMachineTypeFamilies

## 简介

获取实例规格族列表（所有机型的信息）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeHostMachineTypeFamilies)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeHostMachineTypeFamilies`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。如果不填写，则使用默认项目，子账户必须填写。请参阅[GetProjectList界面](https://docs.ucloud.cn/api/summary/get_project_list). |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MachineTypes** | array[[*MachineTypes*](#MachineTypes)] | 机型配置列表 |No|

#### 数据模型


#### MachineTypes

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 机型名称 |No|
| **Description** | string | 机型中文名称 |No|
| **OperationStatus** | string | 机型ComponentCode |No|
| **CpuPlatforms** | array[[*CpuPlatformStatus*](#CpuPlatformStatus)] | CPU平台列表 |No|
| **Disks** | array[[*Disks*](#Disks)] | 磁盘信息 |No|
| **MachineSizes** | array[[*MachineSizes*](#MachineSizes)] | 规格信息 |No|
| **Features** | array[[*Features*](#Features)] | 特性信息 |No|
| **ParentType** | string | 父类型。如GPU机型的父类型为"G" |No|
| **GpuType** | [*FamiliesGpuType*](#FamiliesGpuType) | GPU信息 |No|
| **SceneCategories** | array[string] | 场景分类 |No|
| **GpuSeries** | string | GPU系列 |No|
| **UHostFamilies** | array[[*UHostFamily*](#UHostFamily)] | 规格族信息 |No|
| **Virtual** | boolean | 是否为非真实机型 |No|
| **ProType** | object | 仅OPROG<br />OPRO机型返回 |No|

#### CpuPlatformStatus

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | CPU平台 |No|
| **OperationStatus** | string | 运营Commpont Code |No|

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

#### FamiliesGpuType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 机型名称 |No|
| **GraphicsMemory** | [*GraphicsMemory*](#GraphicsMemory) | 显存信息 |No|
| **Performance** | [*Performance*](#Performance) | 性能信息 |No|

#### UHostFamily

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 规格族 |No|
| **CpuFrequency** | string | CPU频率信息 |No|
| **CpuPlatforms** | array[[*CpuPlatformWithModels*](#CpuPlatformWithModels)] | CPU平台信息 |No|

#### CpuPlatformWithModels

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | CPU平台 |No|
| **CpuModels** | array[string] | CPU Model列表 |No|
| **CpuFrequency** | string | CPU频率 |No|

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
| **BackupMode** | array[string] | 支持的快照备份策略 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeHostMachineTypeFamilies
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=FGdvaxgk
&ProjectId=qNFfwyzn
```

### 响应示例
    
```json
{
  "Action": "DescribeHostMachineTypeFamiliesResponse",
  "MachineTypes": "WshRTkXT",
  "RetCode": 0
}
```





