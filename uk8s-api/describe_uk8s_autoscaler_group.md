# 获取AutoscalerGroup信息 - DescribeUK8SAutoscalerGroup

## 简介

获取autoscaler与auto scaling group信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUK8SAutoscalerGroup`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区，可选。此接口按集群 ID 查询。 |No|
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
| **ScaleDownUnneededTime** | int | 节点持续不需要后触发缩容的等待时间，单位分钟。 |**Yes**|
| **ScaleDownUtilizationThreshold** | int | 节点缩容利用率阈值，单位百分比，范围 0–100。 |**Yes**|
| **ScaleDownDelayAfterAdd** | int | 添加节点后等待缩容的时间，单位分钟。 |**Yes**|
| **Enabled** | int | 打开/关闭 |**Yes**|
| **Version** | string | 伸缩器版本 |**Yes**|
| **UpdateTime** | int | 配置更新时间，Unix 时间戳，单位秒。 |**Yes**|
| **ScaleDownGpuUtilizationThreshold** | int | GPU 缩容利用率阈值，单位百分比，范围 0–100。 |**Yes**|

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
| **MachineType** | string | 云主机机型。 |**Yes**|
| **GPU** | int | GPU 数量。 |**Yes**|
| **GpuType** | string | GPU 类型。 |**Yes**|
| **Labels** | string | 节点标签 key=value,多组用”,“隔开，最多5组 |**Yes**|
| **MaxPods** | int | Pods数量 默认110, 支持16-512 |**Yes**|
| **MinmalCpuPlatform** | string | 最低 CPU 平台的兼容字段，与 MinimalCpuPlatform 相同。 |**Yes**|
| **UHostFamily** | string | 主机规格族 |**Yes**|
| **Min** | int | 最小node数量 |**Yes**|
| **Max** | int | 最大node数量 |**Yes**|
| **CurrentNodeNum** | int | 当前该伸缩组管理的node数量 |**Yes**|
| **CreateTime** | int | 创建时间，Unix 时间戳，单位秒。 |**Yes**|
| **UpdateTime** | int | 更新时间，Unix 时间戳，单位秒。 |**Yes**|
| **ChargeType** | string | 伸缩组的计费模式。 |**Yes**|
| **IsolationGroup** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |**Yes**|
| **Priority** | int | 优先级 |**Yes**|
| **NodeCPU** | int | 节点CPU【兼容】 |No|
| **NodeMem** | int | 节点内存【兼容】 |No|
| **NodeDataDiskType** | string | 节点数据盘类型【兼容】 |No|
| **NodeDataDiskSize** | int | 节点数据盘大小【兼容】 |No|
| **NodeBootDiskType** | string | 旧伸缩组的系统盘类型。 |No|
| **NodeUHostType** | string | 节点云主机机型【兼容】 |No|
| **NodeGroupId** | string | 节点所属节点池id |No|
| **SubnetId** | string | 节点子网id<br />【兼容】 |No|
| **LoginMode** | string | 节点登录方式：Password 或 KeyPair。 |No|
| **KeyPairId** | string | 登录密钥对 ID。 |No|
| **MinimalCpuPlatform** | string | 最低 CPU 平台。 |No|
| **Taints** | string | 节点污点配置。 |No|
| **Tag** | string | 业务组。 |No|
| **ImageId** | string | 镜像 ID。 |No|
| **OsName** | string | 操作系统名称。 |No|
| **UserData** | string | Base64 编码的 cloud-init 用户数据。 |No|
| **InitScript** | string | Base64 编码的节点初始化后脚本。 |No|
| **SecurityMode** | string | 节点安全模式：Firewall 或 SecGroup。 |No|
| **SecGroupId** | array[[*SecGroupId*](#SecGroupId)] | 安全组配置列表。 |No|
| **SecurityGroupId** | string | 防火墙 ID。 |No|
| **NetworkInterface** | array[[*NetworkInterface*](#NetworkInterface)] | 网卡配置列表。 |No|
| **KubeletConfiguration** | [*KubeletConfiguration*](#KubeletConfiguration) | Kubelet 自定义配置。 |No|
| **Password** | string | Base64 编码的节点登录密码。 |No|

#### SecGroupId

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 安全组 ID |No|
| **Name** | string | 安全组名称 |No|
| **Priority** | string | 安全组优先级 |No|

#### NetworkInterface

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EIP** | [*EIP*](#EIP) | EIP |No|

#### KubeletConfiguration

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ContainerLogMaxFiles** | int | 最大日志文件数量 |No|
| **ContainerLogMaxSize** | string | 最大日志文件大小 |No|
| **EvictionHard** | [*EvictionCondition*](#EvictionCondition) | 硬性驱逐条件，EvictionCondition类型 |No|
| **EvictionSoft** | [*EvictionCondition*](#EvictionCondition) | 软性驱逐条件，EvictionCondition类型 |No|
| **EvictionSoftGracePeriod** | [*EvictionCondition*](#EvictionCondition) | 软性驱逐宽限时间，EvictionCondition类型 |No|
| **ImageGCHighThresholdPercent** | int | 镜像垃圾收集阈值 |No|
| **ImageGCLowThresholdPercent** | int | 停止镜像垃圾收集阈值 |No|
| **KubeReserved** | [*ReservedResource*](#ReservedResource) | kubelet预留资源，ReservedResource类型 |No|
| **SystemReserved** | [*ReservedResource*](#ReservedResource) | 系统预留资源，ReservedResource类型 |No|
| **MaxPods** | int | 最大Pod数量 |No|

#### EvictionCondition

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MemoryAvailable** | string | 内存相关驱逐条件或宽限时间。 |No|
| **ImagefsAvailable** | string | 镜像文件系统存储相关驱逐条件或宽限时间。 |No|
| **NodefsAvailable** | string | 节点存储余量相关驱逐条件或宽限时间。 |No|
| **NodefsInodesFree** | string | 节点剩余inodes驱逐条件或宽限时间。 |No|

#### ReservedResource

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CPU** | string | CPU |No|
| **Memory** | string | 内存 |No|
| **EphemeralStorage** | string | 存储 |No|
| **Pid** | string | Pid |No|

#### EIP

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Bandwidth** | int | 【若绑定EIP，此参数必填】弹性IP的外网带宽, 单位为Mbps. 共享带宽模式下非必传, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-300]，带宽计费[1-800] |No|
| **PayMode** | string | 弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. "Free":免费带宽模式,默认为 "Bandwidth" |No|
| **ShareBandwidthId** | string | 绑定的共享带宽Id，仅当PayMode为ShareBandwidth时有效 |No|
| **OperatorName** | string | 【若绑定EIP，此参数必填】弹性IP的线路。枚举值: 国际: International，BGP: Bgp。 各地域允许的线路参数如下: cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International kr-seoul:International us-ws:International ge-fra:International sg:International tw-kh:International.其他海外线路均为 International |No|
| **CouponId** | string | 当前EIP代金券id。请通过DescribeCoupon接口查询，或登录用户中心查看。 |No|

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





