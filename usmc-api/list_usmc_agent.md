# 获取当前用户 Agent 列表 - ListUSMCAgent

## 简介

获取当前用户 Agent 列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUSMCAgent`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PlanId** | string | 迁移计划ID |**Yes**|
| **AgentIds** | string | Agent ID，多个ID以逗号分隔 |No|
| **Offset** | string | 列表起始位置偏移量，默认为0 |No|
| **Limit** | string | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ListAgentItem*](#ListAgentItem)] | [ ]ListAgentItem |**Yes**|

#### 数据模型


#### ListAgentItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AgentId** | string | 客户端ID |No|
| **Name** | string | 客户端名称 |No|
| **Status** | string | 客户端状态 |No|
| **OsData** | [*OSData*](#OSData) | []OSData |No|
| **ResourceData** | [*HostResourceData*](#HostResourceData) | []HostResourceData |No|
| **HostName** | string | 主机名称 |No|
| **Ip** | string | Ip地址 |No|
| **Mac** | string | Mac地址 |No|
| **AgentVerion** | string | 客户端版本号 |No|
| **DiskItems** | array[[*DiskItem*](#DiskItem)] | []DiskItem |No|
| **NetworkType** | int | 网络类型， 10:外网, 20: 内网, 30:专线 |No|
| **TargetRegion** | string | 目标地域 |No|
| **TargetZone** | string | 目标可用区 |No|
| **TargetVPCId** | string | 目标VPC ID |No|
| **TargetSubnetId** | string | 目标子网ID |No|
| **CreateTime** | int | 创建时间 |No|

#### OSData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OsType** | string | 操作系统类型 |No|
| **ArchType** | string | 操作系统架构 |No|
| **PlatformType** | string | 操作系统平台 |No|
| **LinuxVer** | string | Linux版本，仅Linux系统有效 |No|
| **WinVer** | string | Windows版本号，仅Windows系统有效 |No|
| **KernelVersion** | string | 内核版本号 |No|

#### HostResourceData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CpuNums** | int | CPU核数 |**Yes**|
| **MemSize** | int | 内存大小 |**Yes**|
| **MachineType** | string | 机型 |**Yes**|

#### DiskItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Size** | int | 磁盘容量 |No|
| **IsBoot** | boolean | 是否系统盘 |No|
| **DiskType** | string | 磁盘类型 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUSMCAgent
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=EOjyHBuq
&Offset=4
&Limit=9
&Region=BfVjoVSf
&SetId=ZxmoUssh
&AgentIds=oClQQgPk
&AgentIds=tuoDzvuT
&Region=sVvGRkEd
```

### 响应示例
    
```json
{
  "Action": "ListUSMCAgentResponse",
  "Data": {},
  "RetCode": 0
}
```





