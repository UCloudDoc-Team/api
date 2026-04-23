# 获取Clickhouse的创建配置项 - GetUClickhouseClusterCreateOption

## 简介

获取Clickhouse的创建配置项






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUClickhouseClusterCreateOption)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUClickhouseClusterCreateOption`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目Id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*GetCreateUClickhouseClusterOptionResponseData*](#GetCreateUClickhouseClusterOptionResponseData) | 数据 |**Yes**|

#### 数据模型


#### GetCreateUClickhouseClusterOptionResponseData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClickhouseVersions** | array[[*ClickhouseVersion*](#ClickhouseVersion)] | 支持的CK版本 |**Yes**|
| **ClickhouseMachineTypes** | array[[*ClickhouseMachineType*](#ClickhouseMachineType)] | 支持的CK机型 |**Yes**|
| **MaxNodeCount** | int | 实例可创建的最大节点数量 |**Yes**|
| **ZookeeperMachineTypes** | array[[*ClickhouseMachineType*](#ClickhouseMachineType)] | 支持的Zookeeper机型 |**Yes**|

#### ClickhouseVersion

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Version** | string | 版本号 |**Yes**|
| **VersionName** | string | 版本名称 |**Yes**|

#### ClickhouseMachineType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClickhouseMachineTypeName** | string | CK机型名称 |**Yes**|
| **ClickhouseMachineTypeOptions** | array[[*ClickhouseMachineTypeOption*](#ClickhouseMachineTypeOption)] | CK机型可选项 |**Yes**|
| **IsSecgroupMachineType** | string | 机型是否支持安全组 |**Yes**|

#### ClickhouseMachineTypeOption

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClickhouseMachineTypeId** | string | Clickhouse机型ID |**Yes**|
| **MachineType** | string | 机型 |**Yes**|
| **CPU** | int | CPU大小 |**Yes**|
| **Memory** | int | 内存大小，GB |**Yes**|
| **DataDisks** | array[[*ClickhouseDataDisk*](#ClickhouseDataDisk)] | 数据盘列表 |**Yes**|
| **NodeCounts** | array[int] | 允许创建的节点个数 |**Yes**|

#### ClickhouseDataDisk

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskType** | string | 磁盘类型 |**Yes**|
| **MinDiskSize** | int | 最小值，GB |**Yes**|
| **MaxDiskSize** | int | 最大值，GB |**Yes**|
| **DefaultDataDiskSize** | int | 默认大小，GB |**Yes**|
| **Step** | int | 步长，GB |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUClickhouseClusterCreateOption
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=HlkgeMNO
```

### 响应示例
    
```json
{
  "Action": "GetUClickhouseClusterCreateOptionResponse",
  "Data": {},
  "Message": "xMxlfWzv",
  "RetCode": 0
}
```





