# 添加Node节点（云主机） - AddUK8SUHostNode

## 简介

为UK8S集群添加一台Node节点，机型类型为云主机









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUK8SUHostNode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ClusterId** | string | UK8S集群ID。 可从UK8S控制台获取。 |**Yes**|
| **CPU** | int | 虚拟CPU核数。可选参数：2-64（具体机型与CPU的对应关系参照控制台）。默认值: 4。 |**Yes**|
| **Count** | int | 创建Node节点数量，取值范围是[1,50]。 |**Yes**|
| **Password** | string | Node节点密码。请遵照[字段规范](api/uhost-api/specification)设定密码。密码需使用base64进行编码，如下：# echo -n Password1 \| base64 |**Yes**|
| **Mem** | int | 内存大小。单位：MB。范围 ：[4096, 262144]，取值为1024的倍数（可选范围参考控制台）。默认值：8192 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Dynamic，按小时预付费 <br /><br /> > Postpay，按小时后付费（支持关机不收费，目前仅部分可用区支持，请联系您的客户经理） <br /><br /> 默认为月付 |**Yes**|
| **BootDiskType** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **BootDiskSize** | int | 系统盘大小，单位GB。默认40。范围：[40, 500]。注意SSD本地盘无法调整。 |No|
| **DataDiskType** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **DataDiskSize** | int | 数据磁盘大小，单位GB。默认0。范围 ：[20, 1000] |No|
| **Quantity** | int | 购买时长。默认: 1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传0，代表了购买至月末。 |No|
| **MachineType** | string | 云主机机型。枚举值["N", "C", "G", "O", "OS"]。参考[云主机机型说明](api/uhost-api/uhost_type)。 |No|
| **GpuType** | string | GPU类型，枚举值["K80", "P40", "V100",]，MachineType为G时必填 |No|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段（可选范围与MachineType+GpuType相关） |No|
| **Labels** | string | Node节点标签。key=value形式,多组用”,“隔开，最多5组。 如env=pro,type=game |No|
| **MaxPods** | int | 默认110，生产环境建议小于等于110。 |No|
| **IsolationGroup** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |No|
| **ImageId** | string | 镜像 Id，不填时后台程序会自动选用一个可用的镜像 Id，支持用户自定义镜像，自定义镜像必须基于基础镜像制作。 |No|
| **SubnetId** | string | 子网 ID。默认为集群创建时填写的子网ID，也可以填写集群同VPC内的子网ID。 |No|
| **DisableSchedule** | boolean | 用于标示添加完节点后是否将节点临时禁用. 传入 "true" 表示禁用,传入其它或不传表示不禁用 |No|
| **UserData** | string | 用户自定义数据。当镜像支持Cloud-init Feature时可填写此字段。注意：1、总数据量大小不超过 16K；2、使用base64编码。 |No|
| **InitScript** | string | 用户自定义Shell脚本。与UserData的区别在于InitScript在节点初始化完毕后才执行，UserData则是云主机初始化时执行。 |No|
| **MinimalCpuPlatform** | string | 最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"；"Intel/CascadelakeR"; “Amd/Epyc2”,"Amd/Auto"],默认值是"Intel/Auto" |No|
| **Taints** | string | Node节点污点，形式为key=value:effect，多组taints用”,“隔开,最多支持五组。 |No|
| **Tag** | string | 业务组 |No|
| **NodeGroupId** | string | 节点池id |No|
| **SecurityMode** | string | 主机安全模式。Firewall：防火墙；SecGroup：安全组；默认值：Firewall。 |No|
| **NamePrefix** | string | 自定义主机名前缀。完整的自定义主机名为{NamePrefix}-{NodeIP}。 |No|
| **NetCapability** | string | 网络增强特性。枚举值：Normal，不开启; Super，开启网络增强1.0； Ultra，开启网络增强2.0；Extreme，开启网络增强3.0; Infiniband, 开启网络增强4.0（详情参考主机官网文档） |No|
| **UNIFeature** | boolean | 弹性网卡特性。开启了弹性网卡权限位，此特性才生效，默认 false 未开启，true 开启。 |No|
| **NetworkInterface.N.EIP.Bandwidth** | int | 【若绑定EIP，此参数必填】弹性IP的外网带宽, 单位为Mbps. 共享带宽模式下非必传, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-300]，带宽计费[1-800] |No|
| **NetworkInterface.N.EIP.PayMode** | string | 弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. "Free":免费带宽模式,默认为 "Bandwidth" |No|
| **NetworkInterface.N.EIP.ShareBandwidthId** | string | 绑定的共享带宽Id，仅当PayMode为ShareBandwidth时有效 |No|
| **NetworkInterface.N.EIP.OperatorName** | string | 【若绑定EIP，此参数必填】弹性IP的线路。枚举值: 国际: International BGP: Bgp 各地域允许的线路参数如下: cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International kr-seoul:International us-ws:International ge-fra:International sg:International tw-kh:International.其他海外线路均为 International |No|
| **NetworkInterface.N.EIP.CouponId** | string | 当前EIP代金券id。请通过DescribeCoupon接口查询，或登录用户中心查看。 |No|
| **SecurityGroupId** | string | 防火墙ID，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeFirewall](api/unet-api/describe_firewall.html)。 |No|
| **SecGroupId.N.Id** | string | 安全组 ID。至多可以同时绑定5个安全组。 |No|
| **SecGroupId.N.Priority** | string | 安全组优先级。取值范围[1, 5] |No|
| **SecGroupId.N.Name** | string | 安全组名称。 |No|
| **UserLabels** | string | UK8S用户标签，key=value形式,多组用”,“隔开，最多5组。 如env=pro,type=game |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeIds** | array[string] | Node实例Id集合<br /> |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUK8SUHostNode
&Zone=HjafOmlI
&ProjectId=QhySZaWP
&Region=ofGfDPlB
&ClusterId=PDncjlGz
&NodeCpu=3
&NodeNum=4
&Password=immkVITW
&NodeMem=4
&ChargeType=GLtOpVbU
&NodeUHostType=fjbWacib
&NodeBootDiskType=BcUliGXM
&NodeDataDiskType=HkETvOPs
&NodeDataDiskSize=axIciunR
&NodeDiskType=kFeAdCpF
&NodeDiskSize=5
&Quantity=2
&MachineType=MpjsOzvE
&MinmalCpuPlatform=mdRRKIma
&GpuType=PaxzMqMa
&GPU=cXzHPXgm
&Labels=vUeEMXvc
&Kubelet.MaxPods=8
&IsolationGroup=wuiIQmnd
&SubnetId=GziWrdTB
&ImageId=XyBBPJwo
&DisableSchedule=CYWxsWrP
&UserData=hOaOlcSE
&InitScript=QqwXgCtj
&Taints=AySpTyWA
&Tag=madApXSs
&NodeGroupId=ypaIEiSw
&BootDiskSize=9
&NetCapability=vqWxJNNz
&UNIFeature=true
&Nodes.N.NamePrefix=gGxvUuZh
&NamePrefix=HXHdwHmb
&NamePrefix=DWHYqWCV
&NetworkInterface.N.EIP.Bandwidth=nHVuZUEC
&NetworkInterface.N.EIP.PayMode=YYvPUasx
&NetworkInterface.N.EIP.ShareBandwidthId=sISnDiFM
&NetworkInterface.N.EIP.OperatorName=XhfxkrsL
&NetworkInterface.N.EIP.CouponId=sWzBPskc
&SecurityMode=nFkozyNX
&SecGroupId=wQcwsKKA
&NetworkInterface.N.EIP.Bandwidth=hUXdpRbD
&NetworkInterface.N.EIP.PayMode=hYanNvck
&NetworkInterface.N.EIP.ShareBandwidthId=yMwdCowa
&NetworkInterface.N.EIP.OperatorName=SRPAwVoG
&NetworkInterface.N.EIP.CouponId=fqhevYCM
&SecurityMode=paRgxihP
&SecurityGroupId=mrbzSJpX
&SecGroupId.N.Id=CtLNZxND
&SecGroupId.N.Priority=ViZOqzHD
&SecGroupId.N.Name=nxNSncqY
&UserLabels=YOZdrUzx
```

### 响应示例
    
```json
{
  "Action": "AddUK8SUHostNodeResponse",
  "Message": "XcuSztKl",
  "NodeId": [
    "dKbhpRvd"
  ],
  "NodeIds": [
    "WoyWlKQx"
  ],
  "RetCode": 0
}
```





