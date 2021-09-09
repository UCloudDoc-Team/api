# 创建云主机 - CreateUHostInstance

## 简介

创建UHost实例。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUHostInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUHostInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ImageId** | string | 镜像ID。 请通过 [DescribeImage](api/uhost-api/describe_image)获取 |**Yes**|
| **Disks.N.IsBoot** | string | 是否是系统盘。枚举值：<br /><br /> > True，是系统盘 <br /><br /> > False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |**Yes**|
| **Disks.N.Type** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **Disks.N.Size** | int | 磁盘大小，单位GB，必须是10GB的整数倍。请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **Disks.N.BackupType** | string | 磁盘备份方案。枚举值：<br /><br /> > NONE，无备份 <br /><br /> > DATAARK，数据方舟 <br /><br /> > SNAPSHOT（SNAPSHOT模式目前仅在上海C支持），快照 <br /><br />当前磁盘支持的备份模式参考 [磁盘类型](api/uhost-api/disk_type),默认值:NONE |No|
| **Disks.N.Encrypted** | boolean | 【功能仅部分可用区开放，详询技术支持】磁盘是否加密。加密：true, 不加密: false<br />加密必须传入对应的的KmsKeyId,默认值false |No|
| **Disks.N.KmsKeyId** | string | 【功能仅部分可用区开放，详询技术支持】kms key id。选择加密盘时必填。 |No|
| **Disks.N.CouponId** | string | 云盘代金券id。不适用于系统盘/本地盘。请通过DescribeCoupon接口查询，或登录用户中心查看 |No|
| **LoginMode** | string | 主机登陆模式。密码（默认选项）: Password，密钥：KeyPair。 |**Yes**|
| **Password** | string | UHost密码。请遵照[字段规范](api/uhost-api/specification)设定密码。密码需使用base64进行编码，举例如下：# echo -n Password1 \| base64UGFzc3dvcmQx。 |No|
| **Name** | string | UHost实例名称。默认：UHost。请遵照[字段规范](api/uhost-api/specification)设定实例名称。 |No|
| **Tag** | string | 业务组。默认：Default（Default即为未分组）。请遵照[字段规范](api/uhost-api/specification)设定业务组。 |No|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Dynamic，按小时预付费 <br /><br /> > Postpay，按小时后付费（支持关机不收费，目前仅部分可用区支持，请联系您的客户经理） <br /><br />Preemptive计费为抢占式实例 <br /><br /> 默认为月付<br /> |No|
| **Quantity** | int | 购买时长。默认:值 1。按小时购买（Dynamic/Postpay）时无需此参数。 月付时，此参数传0，代表购买至月末。 |No|
| **CPU** | int | 虚拟CPU核数。可选参数：1-64（具体机型与CPU的对应关系参照控制台）。默认值: 4。 |No|
| **Memory** | int | 内存大小。单位：MB。范围 ：[1024, 262144]，取值为1024的倍数（可选范围参考控制台）。默认值：8192 |No|
| **GpuType** | string | GPU类型，枚举值["K80", "P40", "V100", "T4", "T4S","2080Ti","2080Ti-4C","1080Ti", "T4/4", "MI100", "V100S"]，MachineType为G时必填 |No|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段（可选范围与MachineType+GpuType相关） |No|
| **NetCapability** | string | 网络增强特性。枚举值：Normal（默认），不开启;  Super，开启网络增强1.0； Ultra，开启网络增强2.0（仅支持部分可用区，请参考控制台） |No|
| **HotplugFeature** | boolean | 热升级特性。True为开启，False为未开启，默认False。 |No|
| **VPCId** | string | VPC ID。默认为当前地域的默认VPC。 |No|
| **SubnetId** | string | 子网 ID。默认为当前地域的默认子网。 |No|
| **PrivateIp.N** | string | 【数组】创建云主机时指定内网IP。若不传值，则随机分配当前子网下的IP。调用方式举例：PrivateIp.0=x.x.x.x。当前只支持一个内网IP。 |No|
| **SecurityGroupId** | string | 防火墙ID，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeFirewall](api/unet-api/describe_firewall.html)。 |No|
| **IsolationGroup** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |No|
| **AlarmTemplateId** | int | 告警模板id，如果传了告警模板id，且告警模板id正确，则绑定告警模板。绑定告警模板失败只会在后台有日志，不会影响创建主机流程，也不会在前端报错。 |No|
| **MachineType** | string | 云主机机型（V2.0），在本字段和字段UHostType中，仅需要其中1个字段即可。枚举值["N", "C", "G", "O", "OS", "OM", "OPRO", "OMAX", "O.BM", "O.EPC"]。参考[云主机机型说明](api/uhost-api/uhost_type)。 |No|
| **MinimalCpuPlatform** | string | 最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake", "Intel/CascadelakeR", "Intel/IceLake", "Amd/Epyc2", "Amd/Auto"],默认值是"Intel/Auto"。 |No|
| **MaxCount** | int | 本次最大创建主机数量，取值范围是[1,100]，默认值为1。 |No|
| **NetworkInterface.N.EIP.Bandwidth** | int | 【若绑定EIP，此参数必填】弹性IP的外网带宽, 单位为Mbps. 共享带宽模式必须指定0M带宽, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-300]，带宽计费[1-800] |No|
| **NetworkInterface.N.EIP.PayMode** | string | 弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. "Free":免费带宽模式,默认为 "Bandwidth" |No|
| **NetworkInterface.N.EIP.ShareBandwidthId** | string | 绑定的共享带宽Id，仅当PayMode为ShareBandwidth时有效 |No|
| **NetworkInterface.N.EIP.GlobalSSH.Area** | string | 填写支持SSH访问IP的地区名称，如“洛杉矶”，“新加坡”，“香港”，“东京”，“华盛顿”，“法兰克福”。Area和AreaCode两者必填其中之一。 |No|
| **NetworkInterface.N.EIP.GlobalSSH.Port** | int | SSH端口，1-65535且不能使用80，443端口 |No|
| **NetworkInterface.N.EIP.GlobalSSH.AreaCode** | string | GlobalSSH的地区编码，格式为区域航空港国际通用代码。Area和AreaCode两者必填其中之一。 |No|
| **NetworkInterface.N.EIP.OperatorName** | string | 【若绑定EIP，此参数必填】弹性IP的线路。枚举值: 国际: International BGP: Bgp 各地域允许的线路参数如下: cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International kr-seoul:International us-ws:International ge-fra:International sg:International tw-kh:International.其他海外线路均为 International |No|
| **NetworkInterface.N.EIP.CouponId** | string | 当前EIP代金券id。请通过DescribeCoupon接口查询，或登录用户中心查看。 |No|
| **NetworkInterface.N.CreateCernetIp** | boolean | 申请并绑定一个教育网EIP。True为申请并绑定，False为不会申请绑定，默认False。当前只支持具有HPC特性的机型。 |No|
| **UserData** | string | 用户自定义数据。当镜像支持Cloud-init Feature时可填写此字段。注意：1、总数据量大小不超过 16K；2、使用base64编码 |No|
| **AutoDataDiskInit** | string | 数据盘是否需要自动分区挂载。当镜像支持“Cloud-init”Feature时可填写此字段。取值 >“On” 自动挂载（默认值）> “Off” 不自动挂载。 |No|
| **KeyPairId** | string | KeypairId 密钥对ID，LoginMode为KeyPair时此项必须 |No|
| **Features.UNI** | boolean | 弹性网卡特性。开启了弹性网卡权限位，此特性才生效，默认 false 未开启，true 开启，仅与 NetCapability Normal 兼容。 |No|
| **CouponId** | string | 主机代金券ID。请通过DescribeCoupon接口查询，或登录用户中心查看 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UHostIds** | array[string] | UHost实例Id集合 |No|
| **IPs** | array[string] | 【批量创建不会返回】IP信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUHostInstance
&Region=IrPRKVru
&Zone=YxunehQG
&ProjectId=SGGYxkiC
&ImageId=WTrQVOVc
&Disks.N.IsBoot=RprtMlkM
&Disks.N.Type=cTNMVMgN
&Disks.N.Size=4
&LoginMode=ZDxcwBvI
&Password=HjhrLmyV
&Name=kWFfXPdF
&Tag=mZmpwPll
&ChargeType=SVUvekbj
&Quantity=7
&UHostType=xESfaKXW
&CPU=7
&Memory=9
&GpuType=wcdlufLM
&GPU=4
&StorageType=hidVBsZq
&BootDiskSpace=9
&DiskSpace=9
&NetCapability=UAaqyFEH
&TimemachineFeature=yes
&HotplugFeature=true
&DiskPassword=ZhNHQpUa
&NetworkId=CUvjmHLR
&VPCId=INGnMbev
&SubnetId=BzArPHsE
&PrivateIp.N=kINtqkDh
&PrivateMac=kpjksQBp
&SecurityGroupId=jbPxuRXI
&HostType=EMqnGIZZ
&InstallAgent=mOfkpefj
&ResourceType=KCqMZlIl
&Disks.N.BackupType=LiQiEorj
&IsolationGroup=MyYUcDKC
&Disks.N.Encrypted=false
&Disks.N.KmsKeyId=rwVpvLJi
&Disks.N.CouponId=PvRWpaRb
&AlarmTemplateId=2
&MachineType=MJsjIQFC
&MinimalCpuPlatform=VCokccwd
&MaxCount=5
&NetworkInterface.N.EIP.Bandwidth=9
&NetworkInterface.N.EIP.PayMode=JujSAqbO
&NetworkInterface.N.EIP.ShareBandwidthId=kHfdnNWd
&NetworkInterface.N.EIP.GlobalSSH.Area=xyYTjrZB
&NetworkInterface.N.EIP.OperatorName=WNXiYXjc
&NetworkInterface.N.EIP.GlobalSSH.Port=1
&NetworkInterface.N.EIP.CouponId=GFzoXEOo
&NetworkInterface.N.EIP.GlobalSSH.AreaCode=JKcKCFjC
&SetId=1
&HostIp=VxccviHh
&NetworkInterface.N.IPv6.ShareBandwidthId=nYbcxXrf
&UserData=wTkIjHzw
&Disks.N.Id=YnyPnaOj
&AutoDataDiskInit=MynHIYht
&NetworkInterface.N.IPv6.Address=wzQVOnfd
&CharacterName=rDPtrUlu
&PromotionId=iIzhvRBn
&ImageOsName=XojzwILg
&PodId=qwVrfmTT
&BillActivityId=5
&BillActivityRuleId=3
&RestrictMode=kRfUiaKA
&Volumes.N.Type=FKimwmGX
&Volumes.N.IsBoot=zjLJQmIe
&Volumes.N.Size=5
&Volumes.N.VolumeId=lYyhJqrV
&Volumes.N.CouponId=oiISGCSv
&HpcEnhanced=false
&NetworkInterface.N.CreateCernetIp=true
&KeyPairId=gYzfeRZI
&SecGroupId.N=shbyPlMw
&Features.UNI=PCaQdRus
&CouponId=LIgqlYLP
```

### 响应示例
    
```json
{
  "Action": "CreateUHostInstanceResponse",
  "IPs": [
    "iUkWSFjX"
  ],
  "RetCode": 0,
  "UHostIds": [
    "GLKEpaXW"
  ]
}
```





