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

#### KubeProxy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Mode** | string | KubeProxy模式，枚举值为[ipvs,iptables] |No|

#### IPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 国际: Internation，BGP: Bgp，内网: Private |No|
| **IPId** | string | IP资源ID (内网IP无对应的资源ID) |No|
| **IP** | string | IP地址 |No|
| **Bandwidth** | int | IP对应的带宽, 单位: Mb (内网IP不显示带宽信息) |No|
| **Default** | string | 是否默认的弹性网卡的信息。true: 是默认弹性网卡；其他值：不是。 |No|

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
  "CACert": "bgsgUSSj",
  "ClusterDomain": "TrnBlMmf",
  "EtcdCert": "KfWoZCox",
  "EtcdKey": "fcwdvzzi",
  "ExternalApiServer": "GVZVJyHy",
  "KubeProxy": {},
  "MasterResourceStatus": "BBlivSsQ",
  "RetCode": 0,
  "Version": "JSrvWaDf"
}
```





