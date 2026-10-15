# 获取AutoscalerGroup信息 - DescribeUK8SAutoscalerGroup

## 简介

获取autoscaler与auto scaling group信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUK8SAutoscalerGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 【废弃】不需要，需要移除 |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Autoscaler** | [*Autoscaler*](#Autoscaler) | 伸缩器 |**Yes**|
| **AutoScalingGroup** | array[[*AutoScalingGroup*](#AutoScalingGroup)] | 伸缩组列表 |No|
| **Update** | int | 0:无需更新<br />1:有更新<br />2:强制更新 |No|

#### 数据模型


#### Autoscaler

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ScaleDownUnneededTime** | string | 缩容触发延时 |**Yes**|
| **ScaleDownUtilizationThreshold** | string | CPU缩容阈值 |**Yes**|
| **ScaleDownDelayAfterAdd** | string | 静默时间 |**Yes**|
| **Enabled** | int | 打开/关闭 |**Yes**|
| **Version** | string | 伸缩器版本 |**Yes**|
| **UpdateTime** | int |  |**Yes**|
| **ScaleDownGpuUtilizationThreshold** | string | GPU缩容阈值 |**Yes**|

#### AutoScalingGroup

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |**Yes**|
| **Id** | string | 伸缩组ID |**Yes**|
| **Name** | string | 伸缩组名字 |**Yes**|
| **CPU** | int | 节点CPU |**Yes**|
| **Mem** | int | 节点内存 |**Yes**|
| **DataDiskType** | string | 节点数据盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |**Yes**|
| **DataDiskSize** | int | 节点数据盘大小 |**Yes**|
| **BootDiskType** | string | 节点系统盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |**Yes**|
| **BootDiskSize** | int | 节点系统盘大小 |**Yes**|
| **MachineType** | string | 云主机机型（V2.0），枚举值["N", "C", "G"]。 |**Yes**|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段 |**Yes**|
| **GPUType** | string | GPU类型，枚举值["K80", "P40", "V100"] |**Yes**|
| **Labels** | string | 节点标签 key=value,多组用”,“隔开，最多5组 |**Yes**|
| **MaxPods** | int | Pods数量 默认110, 支持16-512 |**Yes**|
| **MinmalCpuPlatform** | string | 最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"。 |**Yes**|
| **UHostFamily** | string | 主机规格族 |**Yes**|
| **Min** | int | 最小node数量 |**Yes**|
| **Max** | int | 最大node数量 |**Yes**|
| **CurrentNodeNum** | int | 当前该伸缩组管理的node数量 |**Yes**|
| **CreateTime** | string | 创建时间 |**Yes**|
| **UpdateTime** | string | 更新时间 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Dynamic，按小时预付费 <br /><br /> > Postpay，按小时后付费（支持关机不收费，目前仅部分可用区支持，请联系您的客户经理） <br /><br />Preemptive计费为抢占式实例 <br /><br /> 默认为月付 |**Yes**|
| **IsolationGroup** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |**Yes**|
| **Priority** | int | 优先级 |**Yes**|
| **NodeCPU** | int | 节点CPU【兼容】 |No|
| **NodeMem** | int | 节点内存【兼容】 |No|
| **NodeDataDiskType** | string | 节点数据盘类型【兼容】 |No|
| **NodeDataDiskSize** | int | 节点数据盘大小【兼容】 |No|
| **NodeBootDiskSize** | string | 节点系统盘类型【兼容】 |No|
| **NodeUHostType** | string | 节点云主机机型【兼容】 |No|
| **NodeGroupId** | string | 节点所属节点池id |No|
| **SubnetId** | string | 节点子网id<br />【兼容】 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUK8SAutoscalerGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=WAKIhOUD
&ClusterId=LkkuwNDN
```

### 响应示例
    
```json
{
  "Action": "DescribeUK8SAutoscalerGroupResponse",
  "AutoScalingGroup": "jkKRcoll",
  "Autoscale": "khQMDnap",
  "RetCode": 0,
  "Update": 9
}
```





