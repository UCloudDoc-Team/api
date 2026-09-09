# 添加UK8S节点池 - AddUK8SNodeGroup

## 简介

添加UK8S节点池









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUK8SNodeGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NodeGroupName** | string | 节点池名字 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|
| **ImageId** | string | 镜像ID |**Yes**|
| **MachineType** | string | 云主机机型。枚举值["N", "C", "G", "O", "OS"]。参考[云主机机型说明](api/uhost-api/uhost_type)。 |**Yes**|
| **CPU** | int | CPU个数 |**Yes**|
| **Mem** | int | 内存大小。单位：MB |**Yes**|
| **BootDiskType** | string | 磁盘类型 |**Yes**|
| **BootDiskSize** | int | 系统盘大小，单位GB。默认40。范围：[40, 500]。注意SSD本地盘无法调整。 |**Yes**|
| **SubnetId** | string | 子网 ID。默认为集群创建时填写的子网ID，也可以填写集群同VPC内的子网ID。 |**Yes**|
| **MinimalCpuPlatform** | string | 最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"；"Intel/CascadelakeR"; “Amd/Epyc2”,"Amd/Auto"],默认值是"Intel/Auto" |No|
| **GpuType** | string | GPU类型 |No|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段（可选范围与MachineType+GpuType相关） |No|
| **DataDiskSize** | int | 数据磁盘大小 |No|
| **DataDiskType** | string | 磁盘类型 |No|
| **Tag** | string | 业务组 |No|
| **ChargeType** | string | 计费模式 |No|
| **UHostFamily** | string | 主机规格族 |No|
| **SecurityMode** | string | 主机安全模式。Firewall：防火墙；SecGroup：安全组；默认值：Firewall。 |No|
| **NodeNamePrefix** | string | 自定义Uhost主机名前缀。完整的自定义Uhost主机名为{NodeNamePrefix}-{NodeIP}。 |No|
| **ZoneBaned** | string | 重复 待删除 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **IsolationGroupId** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |No|
| **MaxPods** | string | 默认110，生产环境建议小于等于110。 |No|
| **UserData** | string | 用户自定义数据。当镜像支持Cloud-init Feature时可填写此字段。注意：1、总数据量大小不超过 16K；2、使用base64编码。 |No|
| **InitScript** | string | 用户自定义Shell脚本。与UserData的区别在于InitScript在节点初始化完毕后才执行，UserData则是云主机初始化时执行。 |No|
| **Taints** | string | Node节点污点，形式为key=value:effect，多组taints用”,“隔开,最多支持五组。 |No|
| **Labels** | string | Node节点标签。key=value形式,多组用”,“隔开，最多5组。 如env=pro,type=game |No|
| **NetCapability** | string | 网络增强特性。枚举值：Normal，不开启; Super，开启网络增强1.0； Ultra，开启网络增强2.0；Extreme，开启网络增强3.0; Infiniband, 开启网络增强4.0（详情参考主机官网文档） |No|
| **UNIFeature** | boolean | 弹性网卡特性。开启了弹性网卡权限位，此特性才生效，默认 false 未开启，true 开启。 |No|
| **SecGroupId.N.Id** | string | 安全组 ID。至多可以同时绑定5个安全组。 |No|
| **SecGroupId.N.Priority** | string | 安全组优先级。取值范围[1, 5] |No|
| **SecGroupId.N.Name** | string | 安全组名称。 |No|
| **SecurityGroupId** | string | 防火墙ID，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeFirewall](api/unet-api/describe_firewall.html)。 |No|
| **NetworkInterface.N.EIP.Bandwidth** | int | 【若绑定EIP，此参数必填】弹性IP的外网带宽, 单位为Mbps. 共享带宽模式下非必传, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-300]，带宽计费[1-800] |No|
| **NetworkInterface.N.EIP.PayMode** | string | 弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. "Free":免费带宽模式,默认为 "Bandwidth" |No|
| **NetworkInterface.N.EIP.ShareBandwidthId** | string | 绑定的共享带宽Id，仅当PayMode为ShareBandwidth时有效 |No|
| **NetworkInterface.N.EIP.OperatorName** | string | 【若绑定EIP，此参数必填】弹性IP的线路。枚举值: 国际: International,BGP: Bgp.<br />各地域允许的线路参数如下: cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International kr-seoul:International us-ws:International ge-fra:International sg:International tw-kh:International.其他海外线路均为 International |No|
| **NetworkInterface.N.EIP.CouponId** | string | 当前EIP代金券id。请通过DescribeCoupon接口查询，或登录用户中心查看。 |No|
| **KubeletConfiguration.ContainerLogMaxFiles** | int | 容器的日志文件个数上限，需大于等于2。控制台展示为containerLogMaxFiles |No|
| **KubeletConfiguration.ContainerLogMaxSize** | string | 容器日志文件轮换生成新文件的最大阈值，需以Mi结尾。控制台展示为containerLogMaxSize |No|
| **KubeletConfiguration.ImageGCHighThresholdPercent** | int | 配置镜像的磁盘用量百分比阈值，一旦镜像用量超过此阈值，镜像垃圾收集会一直运行。<br /><br />取值范围[1, 100], 同时需大于ImageGCLowThresholdPercent取值。控制台展示为imageGCHighThresholdPercent |No|
| **KubeletConfiguration.ImageGCLowThresholdPercent** | int | 配置镜像的磁盘用量百分比阈值，镜像用量低于此阈值时不会执行镜像垃圾收集操作。<br />取值范围[1, 100], 同时需小于imageGCHighThresholdPercent取值。控制台展示为imageGCLowThresholdPercent |No|
| **KubeletConfiguration.MaxPods** | int | Node能运行的Pod最大数量。需大于0。控制台展示为maxPods |No|
| **KubeletConfiguration.EvictionHard.MemoryAvailable** | string | 触发Pod驱逐操作的硬性门限之内存用量: 需以Mi或Gi结尾。控制台展示为evictionHard - memory.available |No|
| **KubeletConfiguration.EvictionHard.ImagefsAvailable** | string | 触发Pod驱逐操作的硬性门限之容器镜像剩余空间: 需以%结尾。控制台展示为evictionHard - imagefs.available |No|
| **KubeletConfiguration.EvictionHard.NodefsAvailable** | string | 触发Pod驱逐操作的硬性门限之节点存储剩余空间: 需以%结尾。控制台展示为evictionHard - nodefs.available |No|
| **KubeletConfiguration.EvictionHard.NodefsInodesFree** | string | 触发Pod驱逐操作的硬性门限节点inode剩余量: 需以%结尾。控制台展示为evictionHard - nodefs.inodesFree |No|
| **KubeletConfiguration.EvictionSoft.MemoryAvailable** | string | 触发Pod驱逐操作的软性门限之内存用量: 需以Mi或Gi结尾。配置此值时必须同时配置EvictionSoftGracePeriod.MemoryAvailable。控制台展示为evictionSoft - memory.available |No|
| **KubeletConfiguration.EvictionSoft.ImagefsAvailable** | string | 触发Pod驱逐操作的软性门限之容器镜像剩余空间: 需以%结尾。配置此值时必须同时配置EvictionSoftGracePeriod.ImagefsAvailable。控制台展示为evictionSoft - imagefs.available |No|
| **KubeletConfiguration.EvictionSoft.NodefsAvailable** | string | 触发Pod驱逐操作的软性门限之节点存储剩余空间: 需以%结尾。配置此值时必须同时配置EvictionSoftGracePeriod.NodefsAvailable。控制台展示为evictionSoft - nodefs.available |No|
| **KubeletConfiguration.EvictionSoft.NodefsInodesFree** | string | 触发Pod驱逐操作的软性门限节点inode剩余量: 需以%结尾。配置此值时必须同时配置EvictionSoftGracePeriod.NodefsInodesFree。控制台展示为evictionSoft - nodefs.inodesFree |No|
| **KubeletConfiguration.EvictionSoftGracePeriod.MemoryAvailable** | string | MemoryAvailable软性门限的宽限时间，必须以s结尾。控制台展示为evictionSoftGracePeriod - memory.available |No|
| **KubeletConfiguration.EvictionSoftGracePeriod.ImagefsAvailable** | string | ImagefsAvailable软性门限的宽限时间，必须以s结尾。控制台展示为evictionSoftGracePeriod - imagefs.available |No|
| **KubeletConfiguration.EvictionSoftGracePeriod.NodefsAvailable** | string | NodefsAvailable软性门限的宽限时间，必须以s结尾。控制台展示为evictionSoftGracePeriod - nodefs.available |No|
| **KubeletConfiguration.EvictionSoftGracePeriod.NodefsInodesFree** | string | NodefsInodesFree软性门限的宽限时间，必须以s结尾。控制台展示为evictionSoftGracePeriod - nodefs.inodesFree |No|
| **KubeletConfiguration.KubeReserved.CPU** | string | kubelet预留CPU资源，以m结尾。控制台展示为kubeReserved - cpu |No|
| **KubeletConfiguration.KubeReserved.Memory** | string | kubelet预留内存资源，以Mi结尾。控制台展示为kubeReserved - memory |No|
| **KubeletConfiguration.KubeReserved.EphemeralStorage** | string | kubelet预留存储空间，以Gi结尾。控制台展示为kubeReserved - ephemeral-storage |No|
| **KubeletConfiguration.KubeReserved.Pid** | string | kubelet预留pid数量，必须大于等于500, string方式提供。控制台展示为kubeReserved - pid |No|
| **KubeletConfiguration.SystemReserved.CPU** | string | 系统预留CPU资源，以m结尾。控制台展示为systemReserved - cpu |No|
| **KubeletConfiguration.SystemReserved.Memory** | string | 系统预留内存资源，以Mi结尾。控制台展示为systemReserved - memory |No|
| **KubeletConfiguration.SystemReserved.EphemeralStorage** | string | 系统预留存储空间，以Gi结尾。控制台展示为systemReserved - ephemeral-storage |No|
| **KubeletConfiguration.SystemReserved.Pid** | string | 系统预留pid数量，必须大于等于500, string方式提供。控制台展示为systemReserved - pid |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeGroupId** | string | 节点池ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUK8SNodeGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=erWPRmTL
&NodeGroupName=sDJQamTw
&ImageId=SErYualz
&MachineType=ulkHtgvq
&MinimalCpuPlatform=llOxqZiy
&CPU=2
&Mem=9
&GpuType=VHPlqtNm
&GPU=7
&BootDiskType=KLbRaYoT
&DataDiskSize=vNWywYIK
&DataDiskType=zdhEnXgA
&Tag=gsZPoUZG
&ChargeType=yhQCTlsM
&ClusterId=tzEjlYyc
&OrgId=8
&TopOrgId=2
&AzGroupId=6
&BootDiskSize=8
&SubnetId=ZASbmHVG
&IsolationGroupId=rVPVzcuA
&MaxPods=IlFXQKpi
&Zone=BQVngVNW
&UserData=YdYsclDf
&InitScript=njpfkDoa
&Taints=JlvPCRQI
&Labels=KeZvvDqr
&NetCapability=ToNrUpTZ
&UNIFeature=true
&SecGroupId=SISNBXEt
&NodeNamePrefix=YsEvGYJy
&NodeNamePrefix=NLzvyZwn
&SecGroupId.N.Priority=hvfZZDWv
&SecGroupId.N.Name=Xskxfpsi
&SecurityMode=ISGiIbEq
&SecurityGroupId=uqsPnEZP
&NetworkInterface.N.EIP.Bandwidth=IJWLkNmH
&NetworkInterface.N.EIP.PayMode=mEgQvaaF
&NetworkInterface.N.EIP.ShareBandwidthId=nUrrbnuU
&NetworkInterface.N.EIP.OperatorName=YqGYAQqd
&NetworkInterface.N.EIP.CouponId=qhIrtbVL
&KubeletConfiguration.ContainerLogMaxFiles=2
&KubeletConfiguration.ContainerLogMaxSize=pQzokxuL
&KubeletConfiguration.ImageGCHighThresholdPercent=1
&KubeletConfiguration.ImageGCLowThresholdPercent=2
&KubeletConfiguration.MaxPods=2
&KubeletConfiguration.ContainerLogMaxFiles=7
&KubeletConfiguration.ContainerLogMaxSize=aGRRIizA
&KubeletConfiguration.ImageGCHighThresholdPercent=2
&KubeletConfiguration.ImageGCLowThresholdPercent=1
&KubeletConfiguration.MaxPods=6
&KubeletConfiguration.EvictionHard.MemoryAvailable=QgsrWvRw
&KubeletConfiguration.EvictionHard.ImagefsAvailable=lsLRZbTm
&KubeletConfiguration.EvictionHard.NodefsAvailable=DMqtzlZh
&KubeletConfiguration.EvictionHard.NodefsInodesFree=IcMWVlJk
&KubeletConfiguration.EvictionSoft.MemoryAvailable=ikYQuqNi
&KubeletConfiguration.EvictionSoft.ImagefsAvailable=rDnxGKDg
&KubeletConfiguration.EvictionSoft.NodefsAvailable=GdGMKqop
&KubeletConfiguration.EvictionSoft.NodefsInodesFree=myCpyBJt
&KubeletConfiguration.EvictionSoft.MemoryAvailable=acNhYicF
&KubeletConfiguration.EvictionSoft.ImagefsAvailable=MAxMTeQI
&KubeletConfiguration.EvictionSoft.NodefsAvailable=EGgCtjiQ
&KubeletConfiguration.EvictionSoft.NodefsInodesFree=TswzCxaT
&KubeletConfiguration.EvictionSoft.MemoryAvailable=AKziQgxI
&KubeletConfiguration.EvictionSoft.ImagefsAvailable=nRujUJRW
&KubeletConfiguration.EvictionSoft.NodefsAvailable=IQvGNHmz
&KubeletConfiguration.EvictionSoft.NodefsInodesFree=EPoRhdQt
&KubeletConfiguration.KubeletConfiguration.MemoryAvailable=EhCrBBAT
&KubeletConfiguration.KubeletConfiguration.ImagefsAvailable=YuKNPiFk
&KubeletConfiguration.KubeletConfiguration.NodefsAvailable=gjFqCMfB
&KubeletConfiguration.KubeletConfiguration.NodefsInodesFree=qPGbvYKW
&KubeletConfiguration.KubeReserved.CPU=AjDXLoCd
&KubeletConfiguration.KubeReserved.Memory=qIajlWXF
&KubeletConfiguration.KubeReserved.EphemeralStorage=wdjSwEdL
&KubeletConfiguration.KubeReserved.Pid=6
&KubeletConfiguration.SystemReserved.CPU=cejkMvfh
&KubeletConfiguration.SystemReserved.Memory=RCpMnKmi
&KubeletConfiguration.SystemReserved.EphemeralStorage=SkCWOsjl
&KubeletConfiguration.SystemReserved.Pid=3
&UHostFamily=oCLJuJjs
```

### 响应示例
    
```json
{
  "Action": "AddUK8SNodeGroupResponse",
  "Message": "DMJPRigX",
  "NodeGroupId": "jXKZQgSU",
  "RetCode": 0
}
```





