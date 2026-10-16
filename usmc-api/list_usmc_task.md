# 获取USMC任务列表 - ListUSMCTask

## 简介

获取USMC任务列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUSMCTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PlanId** | string | 迁移计划ID |**Yes**|
| **Offset** | string | 列表起始位置偏移量，默认为0 |No|
| **Limit** | string | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ListTaskItem*](#ListTaskItem)] | []ListTaskItem |**Yes**|

#### 数据模型


#### ListTaskItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SrcHostName** | string | 源机器名称 |No|
| **SrcHostIp** | string | 源机器IP |No|
| **HostId** | string | 目标机器ID |No|
| **HostIp** | string | 目标机器IP |No|
| **TaskId** | string | 任务ID |No|
| **Name** | string | 任务名称 |No|
| **AgentId** | string | 客户端ID |No|
| **AgentName** | string | 客户端名称 |No|
| **State** | string | 任务状态 |No|
| **AgentState** | string | 客户端状态 |No|
| **Progress** | [*ProgressData*](#ProgressData) | 任务进度 |No|
| **MinimalCpuPlatform** | string | cpu平台 |No|
| **MachineType** | string | 机型 |No|
| **CreateTime** | int | 创建时间 |No|
| **DiskType** | string | 磁盘类型 |No|
| **DataDiskType** | string | 数据盘类型 |No|
| **Gpu** | int | GPU数量 |No|
| **GpuType** | string | GPU类型 |No|
| **Cpu** | int | CPU核数 |No|
| **Memory** | int | 内存大小 |No|
| **UDSetId** | string | 【私有专区属性】专区ID |No|
| **UDHostId** | string | 【私有专区属性】专区宿主机id |No|
| **HostBinding** | boolean | 【私有专区属性】专区云主机开启宿住关联属性 |No|
| **SecGroupId** | array[[*SecGroup*](#SecGroup)] | []SecGroup |No|

#### ProgressData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Percentage** | float | 进度百分比 |No|

#### SecGroup

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 安全组ID |No|
| **Priority** | int | 安全组优先级 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUSMCTask
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=XgqnRSEC
&Offset=7
&Limit=5
&SetId=WdlAPLrt
&NetworkId=xrqzmAQh
```

### 响应示例
    
```json
{
  "Action": "ListUSMCTaskResponse",
  "Data": [
    "jdbaCYcE"
  ],
  "RetCode": 0
}
```





