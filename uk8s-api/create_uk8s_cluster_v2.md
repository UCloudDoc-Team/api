# 创建UK8S集群V2版 - CreateUK8SClusterV2

## 简介

创建UK8S集群









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUK8SClusterV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCId** | string | 集群Node及Pod所属VPC |**Yes**|
| **SubnetId** | string | 集群Node及Pod所属子网 |**Yes**|
| **ServiceCIDR** | string | Service 网段，用于分配ClusterIP，如172.17.0.0/16。该网段不能与集群所属VPC网段重叠。 |**Yes**|
| **ClusterName** | string | 集群名称 |**Yes**|
| **Password** | string | 集群节点密码，包括Master和Node。密码需包含最少一个大写字母，请使用base64进行编码，举例如下：# echo -n Password1 \| base64 |**Yes**|
| **Master.N.Zone** | string | Master节点所属可用区，需要设置 Master.0.Zone、 Master.1.Zone、Master.2.Zone 三个 Master 节点的可用区。 三个节点可部署在不同可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Master.N.SecGroupId.N.Id** | string | 安全组 ID。至多可以同时绑定5个安全组。 |No|
| **Master.N.SecGroupId.N.Priority** | string | 安全组优先级。取值范围[1, 5] |No|
| **Master.N.SecGroupId.N.Name** | string | 安全组名称。 |No|
| **MasterMachineType** | string | Master节点的云主机机型（V2.0），如["N", "C", "O", "OS"]，具体请参照云主机机型。 |**Yes**|
| **MasterCPU** | int | Master节点的虚拟CPU核数。可选参数：2-64（具体机型与CPU的对应关系参照控制台）。 |**Yes**|
| **MasterMem** | int | Master节点的内存大小。单位：MB。范围 ：[4096, 262144]，取值为1024的倍数（可选范围参考控制台）。 |**Yes**|
| **Nodes.N.Zone** | string | 一组Nodes节点所属可用区，可创建多组Nodes节点，如一组是CPU Nodes节点，另一组是GPU Nodes节点。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Nodes.N.MachineType** | string | 一组Nodes节点云主机机型，如["N", "C", "O", "OS"]，具体请参照云主机机型。 |**Yes**|
| **Nodes.N.CPU** | int | 一组Node节点的虚拟CPU核数。单位：核，范围：[2, 64]，可选范围参考控制台。 |**Yes**|
| **Nodes.N.Mem** | int | 一组Node节点的内存大小。单位：MB,范围 ：[4096, 262144]，取值为1024的倍数，可选范围参考控制台。 |**Yes**|
| **Nodes.N.Count** | int | 一组Node节点的数量，范围：[1,10]。 |**Yes**|
| **Nodes.N.IsolationGroup** | string | 一组Node节点的隔离组Id，归属于同一隔离组的虚拟机节点将落在不同的物理机上，单个隔离组最多只能容纳8个节点。参见DescribeIsolationGroup。 |No|
| **Nodes.N.MaxPods** | int | Node节点上可运行最大节点数，默认为110。 |No|
| **Nodes.N.Labels** | string | Node节点标签，形式为key=value，多组Labels用”,“隔开,最多支持五组。 |No|
| **Nodes.N.BootDiskType** | string | 一组Node节点的系统盘类型，请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **Nodes.N.BootDiskSIze** | int | Node节点的系统盘大小，单位GB，默认为40。范围：[40, 500]。注意SSD本地盘无法调整。 |No|
| **Nodes.N.DataDiskType** | string | 一组Node节点的数据盘类型，请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **Nodes.N.GpuType** | string | 一组Node节点的GPU类型，枚举值["K80", "P40", "V100"]，最新值参考Console。 |No|
| **Nodes.N.GPU** | int | 一组Node节点的GPU卡核心数，仅GPU机型支持此字段。 |No|
| **Nodes.N.DataDiskSize** | int | 数据磁盘大小，单位GB。默认0。范围 ：[20, 1000] |No|
| **Nodes.N.MinimalCpuPlatform** | string | Node节点的最低cpu平台，不选则随机。枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"。 |No|
| **Nodes.N.Taints** | string | Node节点污点，形式为key=value:effect，多组taints用”,“隔开,最多支持五组。 |No|
| **Nodes.N.SecurityMode** | string | 主机安全模式。Firewall：防火墙；SecGroup：安全组；默认值：Firewall。 |No|
| **Nodes.N.NamePrefix** | string | 一组Node的自定义主机名前缀。 完整的自定义主机名为{NamePrefix}-{NodeIP}。 |No|
| **Nodes.N.ImageId** | string | Node节点的镜像 ID，不填则使用ImageId参数。支持用户自定义镜像。 |No|
| **Nodes.N.UNIFeature** | string | 弹性网卡特性。开启了弹性网卡权限位，此特性才生效，默认 false 未开启，true 开启。<br /> |No|
| **Nodes.N.NetworkInterface.N.EIP.Bandwidth** | int | 【若绑定EIP，此参数必填】弹性IP的外网带宽, 单位为Mbps. 共享带宽模式下非必传, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-300]，带宽计费[1-800] |No|
| **Nodes.N.NetworkInterface.N.EIP.PayMode** | string | 弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. "Free":免费带宽模式,默认为 "Bandwidth" |No|
| **Nodes.N.NetworkInterface.N.EIP.ShareBandwidthId** | string | 绑定的共享带宽Id，仅当PayMode为ShareBandwidth时有效 |No|
| **Nodes.N.NetworkInterface.N.EIP.OperatorName** | string | 【若绑定EIP，此参数必填】弹性IP的线路。枚举值: 国际: International BGP: Bgp 各地域允许的线路参数如下: cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International kr-seoul:International us-ws:International ge-fra:International sg:International tw-kh:International.其他海外线路均为 International |No|
| **Nodes.N.NetworkInterface.N.EIP.CouponId** | string | 当前EIP代金券id。请通过DescribeCoupon接口查询，或登录用户中心查看。 |No|
| **Nodes.N.SecurityGroupId** | string | 防火墙ID，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeFirewall](api/unet-api/describe_firewall.html)。 |No|
| **Nodes.N.SecGroupId.N.Id** | string | 安全组 ID。至多可以同时绑定5个安全组。 |No|
| **Nodes.N.SecGroupId.N.Priority** | string | 安全组优先级。取值范围[1, 5] |No|
| **Nodes.N.SecGroupId.N.Name** | string | 安全组名称。 |No|
| **MasterBootDiskType** | string | Master节点系统盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **MasterBootDiskSize** | int | Master节点系统盘大小，单位GB，默认为40。范围：[40, 500]。注意SSD本地盘无法调整。 |No|
| **MasterDataDiskType** | string | Master节点数据盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **MasterDataDiskSize** | int | Master节点的数据盘大小，单位GB，默认为0。范围 ：[20, 1000] |No|
| **ChargeType** | string | 集群所有节点的付费模式。枚举值为： Year，按年付费； Month，按月付费； Dynamic，按小时付费（需开启权限），默认按月。 |No|
| **K8sVersion** | string | k8s集群的版本，版本信息请参考UK8S集群创建页，不指定的话默认为当前支持的最高版本。 |No|
| **Quantity** | int | 购买时长。默认为1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传0，代表了购买至月末。 |No|
| **ExternalApiServer** | string | 是否允许外网访问apiserver，开启：Yes 不开启：No。默认为No。 |No|
| **MasterIsolationGroup** | string | 【无效，已删除】当前将自动为Master节点创建隔离组，确保Master节点归属于不同物理机。 |No|
| **KubeProxy.Mode** | string | 集群kube-proxy模式。支持iptables和ipvs，默认为iptables。 |No|
| **ImageId** | string | Master节点和Node节点的镜像 ID，不填则随机选择可用的基础镜像。支持用户自定义镜像。 |No|
| **UserData** | string | 用户自定义数据。注意：1、总数据量大小不超多16K；2、使用base64编码。 |No|
| **InitScript** | string | 用户自定义脚本，与UserData不同，自定义脚本将在集群安装完毕后执行。<br />注意：1、总数据量大小不超多16K；2、使用base64编码。 |No|
| **MasterMinimalCpuPlatform** | string | Master节点的最低cpu平台，不选则随机。枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"。 |No|
| **ClusterDomain** | string | 创建集群的时候定义clusterdomain |No|
| **Tag** | string | 业务组 |No|
| **MasterImageId** | string | Master节点的镜像 ID，不填则使用ImageId参数。支持用户自定义镜像。 |No|
| **LbClass** | string | master lb 类型默认ulb，可选ulb nlb |No|
| **ForwardSrcIPMethod** | string | LbClass为nlb的时候支持的源ip转发模式，目前只支持Toa,为空则不开源ip功能 枚举："",Toa |No|
| **UserLabels** | string | UK8S用户标签，key=value形式,多组用”,“隔开，最多5组。 如env=pro,type=game |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterId** | string | 集群ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUK8SClusterV2
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=DUYLbuwj
&VPCId=NIUbMRrP
&SubnetId=oWAtQljO
&ServiceCIDR=iXXMZpXs
&ClusterName=gcuwXSLm
&Password=vDsbRNNQ
&ChargeType=TrFaoDAK
&Quantity=PxBiAWAo
&K8sVersion=uxAueotm
&ExternalApiServer=vasrSAjn
&Master.1.zone=rwFzpSWL
&Master.2.zone=MuzxrYho
&Master.3.zone=blItdpQD
&MasterMachineType=rBCZRPYI
&MasterMinmalCpuPlatform=wJoUcbYp
&MasterCPU=oKqzqZZh
&MasterMem=hwUjKpoK
&MasterBootDiskType=jbQIKkul
&MasterDataDiskType=RmHtwyLG
&MasterDataDiskSize=NFuIPJcm
&Nodes.N.zone=hDtZnELL
&Nodes.N.MachineType=MMuaNZIl
&Nodes.N.MinmalCpuPlatform=uLWsDWDL
&Nodes.N.GpuType=mXrWwOLD
&Nodes.N.GPU=nRsbGDlh
&Nodes.N.CPU=CiNwWCeJ
&Nodes.N.Mem=ZgEuxdnu
&Nodes.N.BootDiskType=VQGewTRm
&K8sVersion=UOoiKtNm
&ExternalApiServer=RVgMWokk
&Master.1.zone=wXjbFYSU
&Master.2.zone=YvijQPFd
&Master.3.zone=CAIJnJEp
&MasterMachineType=SiECGsDX
&MasterMinmalCpuPlatform=kElumqZJ
&MasterCPU=ODBnDKWv
&MasterMem=IQKJEydV
&MasterBootDiskType=rqEFOgqz
&MasterDataDiskType=qCJOPxEF
&MasterDataDiskSize=tkpcQGJS
&Nodes.N.zone=aLzNslLv
&Nodes.N.MachineType=hCtXDpwx
&Nodes.N.MinmalCpuPlatform=hhfNYZAU
&Nodes.N.GpuType=lEgwfaMY
&Nodes.N.GPU=pXervTpu
&Nodes.N.CPU=TqeQgstN
&Nodes.N.Mem=AhdyTtIB
&Nodes.N.BootDiskType=ePIgbSGU
&Nodes.N.DataDiskType=jLNDJqhX
&Nodes.N.DataDiskSize=2
&Nodes.N.Counts=6
&Nodes.N.DataDiskType=OlCnwgED
&Nodes.N.DataDiskSize=1
&Nodes.N.Count=4
&Nodes.N.IsolationGroup=lRBbaDzS
&Nodes.N.MaxPods=3
&Nodes.N.Labels=CqzkeSQm
&MasterIsolationGroup=dDOFtdaB
&KubeProxy.Mode=GIDxitAX
&Master.1.ImageId=ABQAxkZu
&Master.2.ImageId=fkxnCKWb
&Master.0.ImageId=uUDUNHsr
&Nodes.0.ImageId=awZnTxun
&Master.1.ImageId=iYqiafUe
&Master.2.ImageId=LkAIwJWg
&Master.0.ImageId=pakiLuEz
&Nodes.N.ImageId=BcMswTGF
&UserData=owngUkKm
&InitScript=SbzevruM
&ClusterDomain=ttXFgIDH
&Nodes.N.Taints=aoCdpgSC
&Tag=PCyjOmac
&MasterBootDiskSize=7
&Nodes.N.BootDiskSIze=9
&CNIMode=HQAhnibp
&PodCIDR=LkIFfqBU
&IPBlockSize=yPTYRITN
&CrossSubnetOverlay=ykfkUtYe
&DedicatedPodSubnet=true
&PodSubnetId=AtLKBDZC
&PodSubnetSecGroup=voVhGwAs
&Nodes.N.UNIFeature=tcXYRfSf
&MasterImageId=KRCMIYAZ
&Nodes.N.ImageId=mIwEOFSN
&LbClass=XgLGNVvn
&ForwardSrcIPMethod=jMmCcbym
&Nodes.N.NamePrefix=JjocQScJ
&Nodes.N.NamePrefix=zEOlQeni
&Master.N.SecGroupId.N.Id=IcmLJdGu
&Master.N.SecGroupId.N.Priority=cfpFfBav
&Master.N.SecGroupId.N.Name=UaqXcFZZ
&Nodes.N.NetworkInterface.N.EIP.Bandwidth=EZnVoNAw
&Nodes.N.NetworkInterface.N.EIP.PayMode=gwQwKZlT
&Nodes.N.NetworkInterface.N.EIP.ShareBandwidthId=paDAphwE
&Nodes.N.NetworkInterface.N.EIP.OperatorName=SJMUIxis
&Nodes.N.NetworkInterface.N.EIP.CouponId=tHvQXoED
&Nodes.N.SecurityMode=uUgueXIj
&Nodes.N.SecurityGroupId=QHcmcRAP
&Nodes.N.SecGroupId.N.Id=WOkeFmEP
&Nodes.N.SecGroupId.N.Priority=gpPFbYmv
&Nodes.N.SecGroupId.N.Name=paIynhHT
&UserLabels=vJsZlNcH
```

### 响应示例
    
```json
{
  "Action": "CreateUK8SClusterV2Response",
  "ClusterId": "cFlgBOGW",
  "RetCode": 0
}
```





