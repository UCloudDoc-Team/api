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
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **VPCId** | string | 集群Node及Pod所属VPC |**Yes**|
| **SubnetId** | string | 集群Node及Pod所属子网 |**Yes**|
| **ServiceCIDR** | string | Service 网段，用于分配ClusterIP，如172.17.0.0/16。该网段不能与集群所属VPC网段重叠。 |**Yes**|
| **ClusterName** | string | 集群名称 |**Yes**|
| **Password** | string | 集群节点密码，包括Master和Node。密码需包含最少一个大写字母，请使用base64进行编码，举例如下：# echo -n Password1 \| base64 |**Yes**|
| **Master.N.Zone** | string | Master节点所属可用区，需要设置 Master.0.Zone、 Master.1.Zone、Master.2.Zone 三个 Master 节点的可用区。 三个节点可部署在不同可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **MasterMachineType** | string | Master节点的云主机机型（V2.0），如["N", "C", "O", "OS"]，具体请参照云主机机型。 |**Yes**|
| **MasterCPU** | int | Master节点的虚拟CPU核数。可选参数：2-64（具体机型与CPU的对应关系参照控制台）。 |**Yes**|
| **MasterMem** | int | Master节点的内存大小。单位：MB。范围 ：[4096, 262144]，取值为1024的倍数（可选范围参考控制台）。 |**Yes**|
| **Nodes.N.Zone** | string | 一组Nodes节点所属可用区，可创建多组Nodes节点，如一组是CPU Nodes节点，另一组是GPU Nodes节点。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **Nodes.N.MachineType** | string | 一组Nodes节点云主机机型，如["N", "C", "O", "OS"]，具体请参照云主机机型。 |**Yes**|
| **Nodes.N.CPU** | int | 一组Node节点的虚拟CPU核数。单位：核，范围：[2, 64]，可选范围参考控制台。 |**Yes**|
| **Nodes.N.Mem** | int | 一组Node节点的内存大小。单位：MB,范围 ：[4096, 262144]，取值为1024的倍数，可选范围参考控制台。 |**Yes**|
| **Nodes.N.Count** | int | 一组Node节点的数量，范围：[1,10]。 |**Yes**|
| **Nodes.N.IsolationGroup** | string | 一组Node节点的隔离组Id，归属于同一隔离组的虚拟机节点将落在不同的物理机上，单个隔离组最多只能容纳8个节点。参见DescribeIsolationGroup。 |No|
| **Nodes.N.MaxPods** | int | Node节点上可运行最大节点数，默认为110。 |No|
| **Nodes.N.Labels** | string | Node节点标签，形式为key=value，多组Labels用”,“隔开,最多支持五组。 |No|
| **Nodes.N.BootDiskType** | string | 一组Node节点的系统盘类型，请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **Nodes.N.DataDiskType** | string | 一组Node节点的数据盘类型，请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **Nodes.N.MinmalCpuPlatform** | string | Node节点的最低cpu平台，不选则随机。枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"。 |No|
| **Nodes.N.GpuType** | string | 一组Node节点的GPU类型，枚举值["K80", "P40", "V100"]，最新值参考Console。 |No|
| **Nodes.N.GPU** | int | 一组Node节点的GPU卡核心数，仅GPU机型支持此字段。 |No|
| **Nodes.N.DataDiskSize** | int | 数据磁盘大小，单位GB。默认0。范围 ：[20, 1000] |No|
| **MasterBootDiskType** | string | Master节点系统盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **MasterDataDiskType** | string | Master节点数据盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **MasterMinmalCpuPlatform** | string | Master节点的最低cpu平台，不选则随机。枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"。 |No|
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
```

### 响应示例
    
```json
{
  "Action": "CreateUK8SClusterV2Response",
  "ClusterId": "cFlgBOGW",
  "RetCode": 0
}
```





