# 获取可用机型 - GetUK8SAvailableInstanceTypes

## 简介

获取uk8s节点可用机型






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUK8SAvailableInstanceTypes`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Status** | string | 当前区域是否可售 |No|
| **AvailableInstanceTypes** | array[[*UK8SAvailableInstanceType*](#UK8SAvailableInstanceType)] | UK8S 支持的可用机型列表 |No|

#### 数据模型


#### UK8SAvailableInstanceType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **Name** | string | 机型名称 |No|
| **Status** | string | 机型状态 |No|
| **Description** | string | 机型描述 |No|
| **UHostFamilies** | array[[*InstanceTypeUHostFamily*](#InstanceTypeUHostFamily)] | 主机系列列表 |No|
| **Disks** | array[[*InstanceTypeDisk*](#InstanceTypeDisk)] | 支持的磁盘配置 |No|
| **MachineSizes** | array[[*InstanceTypeMachineSize*](#InstanceTypeMachineSize)] | 支持的机型规格 |No|
| **Features** | array[[*InstanceTypeFeature*](#InstanceTypeFeature)] | 机型特性列表 |No|
| **MachineClass** | string | 机型类别 |No|
| **InstanceType** | string | 实例类型 |No|
| **ParentType** | string | 父机型类型 |No|
| **GraphicsMemory** | [*InstanceTypeValueRate*](#InstanceTypeValueRate) | 显存信息 |No|
| **Performance** | [*InstanceTypeValueRate*](#InstanceTypeValueRate) | 性能信息 |No|

#### InstanceTypeUHostFamily

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 规格族名称 |No|
| **CpuFrequency** | string | CPU 频率 |No|
| **CpuPlatforms** | array[[*InstanceTypeCpuPlatform*](#InstanceTypeCpuPlatform)] | 支持的 CPU 平台 |No|

#### InstanceTypeDisk

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 磁盘配置名称 |No|
| **BootDisk** | array[[*InstanceTypeBootDisk*](#InstanceTypeBootDisk)] | 支持的系统盘配置 |No|
| **DataDisk** | array[[*InstanceTypeDataDisk*](#InstanceTypeDataDisk)] | 支持的数据盘配置 |No|

#### InstanceTypeMachineSize

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Gpu** | int | GPU 数量 |No|
| **Collection** | array[[*InstanceTypeMachineSizeCollection*](#InstanceTypeMachineSizeCollection)] | CPU 与内存规格组合 |No|

#### InstanceTypeFeature

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 特性名称 |No|
| **Modes** | array[[*InstanceTypeFeatureMode*](#InstanceTypeFeatureMode)] | 特性模式列表 |No|

#### InstanceTypeValueRate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Value** | float | 数值 |No|
| **Rate** | int | 评分 |No|

#### InstanceTypeFeatureMode

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 模式名称 |No|
| **RelatedToImageFeature** | array[string] | 关联的镜像特性 |No|
| **MinimalCpuPlatform** | array[string] | 最低 CPU 平台列表 |No|

#### InstanceTypeMachineSizeCollection

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Cpu** | int | CPU 核数 |No|
| **Memory** | array[int] | 可用内存容量列表 |No|
| **MinimalCpuPlatform** | array[string] | 最低 CPU 平台列表 |No|

#### InstanceTypeBootDisk

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 系统盘类型名称 |No|
| **InstantResize** | boolean | 是否支持即时扩容 |No|
| **MaximalSize** | int | 最大磁盘容量 |No|
| **Features** | array[string] | 磁盘特性列表 |No|

#### InstanceTypeDataDisk

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 数据盘类型名称 |No|
| **MinimalSize** | int | 最小磁盘容量 |No|
| **MaximalSize** | int | 最大磁盘容量 |No|
| **Features** | array[string] | 磁盘特性列表 |No|

#### InstanceTypeCpuPlatform

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | CPU 平台名称 |No|
| **CpuModels** | array[string] | CPU 型号列表 |No|
| **CpuFrequency** | string | CPU 频率 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUK8SAvailableInstanceTypes
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=yCiRMcyT
```

### 响应示例
    
```json
{
  "Action": "GetUK8SAvailableInstanceTypesResponse",
  "AvailableInstanceTypes": [
    "RxpeRdCZ"
  ],
  "RetCode": 0,
  "Status": "OCKLEmML"
}
```





