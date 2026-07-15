# 获取集群信息 - DescribeUK8SCluster

## 简介

获取集群信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUK8SCluster`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 所属区域 |**Yes**|
| **ProjectId** | string | 项目id |No|
| **ClusterId** | string | k8s集群ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterName** | string | 资源名字 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|
| **VPCId** | string | 所属VPC |**Yes**|
| **SubnetId** | string | 所属子网 |**Yes**|
| **PodCIDR** | string | Pod网段 |**Yes**|
| **ServiceCIDR** | string | 服务网段 |**Yes**|
| **MasterCount** | int | Master 节点数量 |**Yes**|
| **MasterList** | array[[*UhostInfo*](#UhostInfo)] | Master节点配置信息，具体参考UhostInfo。托管版不返回该信息 |No|
| **NodeList** | array[[*UhostInfo*](#UhostInfo)] | Node节点配置信息,具体参考UhostInfo |No|
| **CreateTime** | int | 创建时间 |No|
| **NodeCount** | int | Node节点数量 |No|
| **ApiServer** | string | 集群apiserver地址 |No|
| **Status** | string | 状态 |No|
| **ExternalApiServer** | string | 集群外部apiserver地址 |No|
| **KubeProxy** | [*KubeProxy*](#KubeProxy) | kube-proxy配置 |No|
| **Version** | string | K8S版本 |No|
| **ClusterDomain** | string | 自定义或者默认的clusterdomain |No|
| **EtcdCert** | string | 集群etcd服务证书 |No|
| **EtcdKey** | string | 集群etcd服务密钥 |No|
| **CACert** | string | 集群CA根证书 |No|
| **MasterResourceStatus** | string | Master配置预警：Normal正常；<br />Warning 需要升级；<br />Error    需要紧急升级； |No|
| **CNIMode** | string | CNI模式，可选值VPC/Calico |No|
| **MonitorType** | string | 集群的监控类型：no无监控；cloudwatch统一监控平台；prometheus内置监控 |No|
| **Autoscaler** | [*Autoscaler*](#Autoscaler) | 集群的节点伸缩(CA)配置 |No|
| **EnableUserAuth** | boolean | 是否开启了授权管理功能 |No|
| **DedicatedPodSubnet** | boolean | Pod是否使用独立子网 |No|
| **PodSubnetIds** | array[string] | Pod使用的独立子网列表 |No|
| **DeleteProtection** | int | 删除保护开关。0表示不开启，1表示开启。默认不开启 |No|
| **PodSubnetSecGroups** | array[string] | Pod独立子网内的ip使用的安全组 |No|
| **NodeCIDR** | string | 节点网段 |No|
| **ExternalUlb** | string | 外部 API Server 负载均衡实例 ID |No|
| **InternalUlb** | string | 内部 API Server 负载均衡实例 ID |No|
| **UpdateTime** | int | 更新时间 |No|
| **LbClass** | string | 负载均衡类型 |No|
| **RuntimeName** | string | 容器运行时名称 |No|
| **RuntimeVersion** | string | 容器运行时版本 |No|
| **ClusterType** | string | 集群版本 |No|
| **LoopbackClientCert** | [*LoopbackClientCert*](#LoopbackClientCert) | API Server 回环客户端证书 |No|

#### 数据模型


#### UhostInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 所在机房 |**Yes**|
| **Name** | string | 主机名称 |**Yes**|
| **CPU** | int | Cpu数量 |**Yes**|
| **Memory** | int | 内存 |**Yes**|
| **IPSet** | array[[*IPSet*](#IPSet)] | 节点IP信息 |**Yes**|
| **DiskSet** | array[[*DiskSet*](#DiskSet)] | 节点磁盘信息 |**Yes**|
| **NodeId** | string | 主机ID |**Yes**|
| **OsName** | string | 镜像信息 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ExpireTime** | int | 到期时间 |**Yes**|
| **State** | string | 主机状态 |**Yes**|
| **NodeType** | string | 节点类型：uhost表示云主机;uphost表示物理云主机 |**Yes**|
| **GPU** | int | GPU 数量 |**Yes**|
| **GpuType** | string | GPU 型号 |**Yes**|
| **BasicImageName** | string | 基础镜像名称 |**Yes**|
| **OsType** | string | 操作系统类型 |**Yes**|
| **TotalDiskSpace** | int | 节点总磁盘空间 |**Yes**|
| **MachineType** | string | 主机机型类别 |**Yes**|
| **SecGroupId** | array[[*SecGroupId*](#SecGroupId)] | 节点关联的安全组列表 |**Yes**|

#### KubeProxy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Mode** | string | KubeProxy模式，枚举值为[ipvs,iptables] |No|

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

#### LoopbackClientCert

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ExpireTime** | int | 证书到期时间 |No|
| **Warn** | boolean | 证书是否进入过期告警状态 |No|

#### IPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 国际: Internation，BGP: Bgp，内网: Private |No|
| **IPId** | string | IP资源ID (内网IP无对应的资源ID) |No|
| **IP** | string | IP地址 |No|
| **Bandwidth** | int | IP对应的带宽, 单位: Mb (内网IP不显示带宽信息) |No|
| **Default** | string | 是否默认的弹性网卡的信息。true: 是默认弹性网卡；其他值：不是。 |No|
| **IPMode** | string | IP 地址分配模式 |No|
| **VPCId** | string | IP 所属的 VPC Id |No|
| **SubnetId** | string | IP 所在的 子网 Id |No|
| **Mac** | string | 网卡的 MAC 地址 |No|
| **NetworkInterfaceId** | string | 虚拟网卡 Id |No|

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

#### SecGroupId

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 安全组名称 |No|
| **Name** | string | 安全组id |No|
| **Priority** | string | 安全组优先级 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUK8SCluster
&Region=zfXlbPNP
&Zone=dSenpJQB
&ClusterID=kCvoCLjV
```

### 响应示例
    
```json
{
  "Action": "DescribeUK8SClusterResponse",
  "Autoscaler": {},
  "CACert": "bgsgUSSj",
  "CNIMode": "lhkRDcNM",
  "ClusterDomain": "TrnBlMmf",
  "DedicatedPodSubnet": true,
  "DeleteProtection": 5,
  "EnableUserAuth": true,
  "EtcdCert": "KfWoZCox",
  "EtcdKey": "fcwdvzzi",
  "ExternalApiServer": "GVZVJyHy",
  "KubeProxy": {},
  "MasterResourceStatus": "BBlivSsQ",
  "MonitorType": "XjdGMetb",
  "PodSubnetIds": [
    "zVCBFDyV"
  ],
  "PodSubnetSecGroups": [
    "nOXEdkfR"
  ],
  "RetCode": 0,
  "UserAuthable": false,
  "Version": "JSrvWaDf"
}
```





