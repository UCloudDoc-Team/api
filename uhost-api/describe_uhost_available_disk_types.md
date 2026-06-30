# 获取主机可挂载的磁盘信息 - DescribeUHostAvailableDiskTypes

## 简介

获取主机可挂载的磁盘信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUHostAvailableDiskTypes)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUHostAvailableDiskTypes`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostIds.N** | string | 实例Id列表。最多100个 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DiskTypeSet** | array[[*AvailableDiskTypes*](#AvailableDiskTypes)] | 可挂载的磁盘信息列表 |**Yes**|

#### 数据模型


#### AvailableDiskTypes

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **UHostId** | string | 实例Id |No|
| **AvailableDisks** | array[[*Disks*](#Disks)] | 可用磁盘信息 |No|

#### Disks

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 磁盘介质类别信息，磁盘主要分类如下：云盘\|cloudDisk、普通本地盘\|normalLocalDisk和SSD本地盘\|ssdLocalDisk。  |No|
| **BootDisk** | array[[*BootDiskInfo*](#BootDiskInfo)] | 系统盘信息 |No|
| **DataDisk** | array[[*DataDiskInfo*](#DataDiskInfo)] | 数据盘信息 |No|

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
https://api.ucloud.cn/?Action=DescribeUHostAvailableDiskTypes
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=aapnFXdm
&UHostIds.N=DgUleNLt
```

### 响应示例
    
```json
{
  "Action": "DescribeUHostAvailableDiskTypesResponse",
  "DiskTypeSet": [
    "ozwaOjxe"
  ],
  "RetCode": 0
}
```





