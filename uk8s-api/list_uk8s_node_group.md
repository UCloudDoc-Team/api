# 列出UK8S节点池 - ListUK8SNodeGroup

## 简介

列出UK8S节点池









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUK8SNodeGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeGroupList** | array[[*NodeGroupSet*](#NodeGroupSet)] | 节点池列表 |No|

#### 数据模型


#### NodeGroupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **NodeGroupId** | string | 节点池ID |No|
| **NodeGroupName** | string | 节点池名字 |No|
| **NodeNamePrefix** | string | 自定义Uhost主机名前缀。完整的自定义Uhost主机名为{NodeNamePrefix}-{NodeIP}。 |No|
| **ImageId** | string | 镜像ID |No|
| **MachineType** | string | 机型 |No|
| **MinimalCpuPlatform** | string | cpu平台 |No|
| **UHostFamily** | string | 主机规格族 |No|
| **CPU** | int | 虚拟CPU核数 |No|
| **Mem** | int | 内存大小 |No|
| **GpuType** | string | GPU类型 |No|
| **GPU** | int | GPU卡核心数 |No|
| **BootDiskType** | string | 系统盘类型 |No|
| **BootDiskSize** | int | 系统盘大小 |No|
| **DataDiskSize** | int | 数据盘大小 |No|
| **DataDiskType** | string | 数据盘类型 |No|
| **Tag** | string | 业务组 |No|
| **ChargeType** | string | 付费方式 |No|
| **NodeList** | array[string] | 节点id列表 |No|
| **SubnetId** | string | 子网 ID。默认为集群创建时填写的子网ID，也可以填写集群同VPC内的子网ID。 |No|
| **IsolationGroupId** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |No|
| **MaxPods** | int | int<br />默认110，生产环境建议小于等于110。 |No|
| **UserData** | string | 用户自定义数据。当镜像支持Cloud-init Feature时可填写此字段。注意：1、总数据量大小不超过 16K；2、使用base64编码。 |No|
| **InitScript** | string | 用户自定义Shell脚本。与UserData的区别在于InitScript在节点初始化完毕后才执行，UserData则是云主机初始化时执行。 |No|
| **Taints** | string | Node节点污点，形式为key=value:effect，多组taints用”,“隔开,最多支持五组。 |No|
| **Labels** | string | Node节点标签。key=value形式,多组用”,“隔开，最多5组。 如env=pro,type=game |No|
| **SecGroupId** | array[[*SecGroupId*](#SecGroupId)] | Node所属的安全组id（最多5个） |No|
| **SecurityMode** | string | 主机安全模式。Firewall：防火墙；SecGroup：安全组；默认值：Firewall。 |No|
| **SecurityGroupId** | string | 防火墙ID，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeFirewall](api/unet-api/describe_firewall.html)。 |No|
| **NetworkInterface** | array[[*NetworkInterface*](#NetworkInterface)] | Node节点网卡配置 |No|
| **KubeletConfiguration** | [*KubeletConfiguration*](#KubeletConfiguration) | KubeletConfiguration |No|
| **ImageName** | string | 镜像名称 |No|
| **ImageType** | string | 镜像类型 |No|
| **OsType** | string | 操作系统类型 |No|
| **OsName** | string | 操作系统名称 |No|
| **NetCapability** | string | 网络配置 |No|
| **UNIFeature** | boolean | 是否启用 UNI 网络特性 |No|
| **Disks** | array[[*DiskSet*](#DiskSet)] | 磁盘列表 |No|
| **RelatedAsg** | array[string] | 节点池关联的弹性伸缩组ID |No|
| **CreateTime** | int | 节点池创建时间 |No|
| **UpdateTime** | int | 节点池更新时间 |No|

#### SecGroupId

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 安全组名称 |No|
| **Name** | string | 安全组id |No|
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

#### DiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 磁盘类型。系统盘: Boot，数据盘: Data,网络盘：Udisk |No|
| **DiskId** | string | 磁盘长ID |No|
| **Name** | string | UDisk名字（仅当磁盘是UDisk时返回） |No|
| **Drive** | string | 磁盘盘符 |No|
| **Size** | int | 磁盘大小，单位: GB |No|
| **BackupType** | string | 备份方案，枚举类型：BASIC_SNAPSHOT,普通快照；DATAARK,方舟。无快照则不返回该字段。 |No|
| **IOPS** | int | 当前主机的IOPS值 |No|
| **Encrypted** | string | Yes: 加密 No: 非加密 |No|
| **DiskType** | string | LOCAL_NOMAL\| CLOUD_NORMAL\| LOCAL_SSD\| CLOUD_SSD\|EXCLUSIVE_LOCAL_DISK |No|
| **IsBoot** | string | True\| False |No|

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
https://api.ucloud.cn/?Action=ListUK8SNodeGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=wVpiDplE
&ClusterId=RXIkKKuX
&TopOrgId=8
&OrgId=4
&AzGroup=5
```

### 响应示例
    
```json
{
  "Action": "ListUK8SNodeGroupResponse",
  "NodeGroupList": [
    {
      "BootDiskType": "ceGeUMIV",
      "CPU": 6,
      "ChargeType": "addNhDvH",
      "DataDiskSize": 8,
      "DataDiskType": "qqncHfyc",
      "GPU": 7,
      "GpuType": "neHNFfsx",
      "ImageId": "PVoCRmtW",
      "MachineType": "GJXNpRmz",
      "Mem": 7,
      "MinimalCpuPlatform": "uEqOcnpP",
      "NodeGroupId": "ayLygrGZ",
      "NodeGroupName": "svwqEVOH",
      "NodeList": "ndxnQQhO",
      "Tag": "XUcqKwjh"
    }
  ],
  "RetCode": 0
}
```





