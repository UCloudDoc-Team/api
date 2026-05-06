# 主机创建资源余量检查 - CheckUHostResourceCapacity

## 简介

主机创建资源余量检查






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CheckUHostResourceCapacity)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CheckUHostResourceCapacity`                        | **Yes** |
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
| **Disks.N.Size** | int | 磁盘大小，单位GB。请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **Disks.N.BackupType** | string | 磁盘备份方案。枚举值：<br /><br /> > NONE，无备份 <br /><br /> > DATAARK，数据方舟 <br /><br /> > SNAPSHOT，快照 <br /><br />当前磁盘支持的备份模式参考 [磁盘类型](api/uhost-api/disk_type),默认值:NONE |No|
| **Disks.N.CouponId** | string | 云盘代金券id。不适用于系统盘/本地盘。请通过DescribeCoupon接口查询，或登录用户中心查看 |No|
| **Disks.N.BackupMode** | string | 指定快照备份策略。当Disks.N.BackupType为"SNAPSHOT"时此参数生效。枚举值："Lite"：轻量版，"Base"：基础版，"Ultimate"：旗舰版，"Custom"：自定义备份链；默认值："Base" |No|
| **Disks.N.CustomBackup.Journal** | string | Disks.N.BackupMode为"Custom"时，进行设置, 以12小时秒级为基础进行倍数扩增，如12、24、36、48。 |No|
| **Disks.N.CustomBackup.Hour** | string | Disks.N.BackupMode为"Custom"时，进行设置, 以24小时级为基础进行倍数扩增，如24、48、72、96。 |No|
| **Disks.N.CustomBackup.Day** | string | Disks.N.BackupMode为"Custom"时，进行设置, 以5天级为基础进行倍数扩增，如5、10、15、20、25、30。 |No|
| **Disks.N.SnapshotId** | string | 从快照创建盘时所用快照id，目前仅支持数据盘 |No|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Dynamic，按小时预付费 <br /><br /> > Postpay，按小时后付费（支持关机不收费，目前仅部分可用区支持，请联系您的客户经理） <br /><br /> > Spot计费为抢占式实例(内测阶段) <br /><br /> 默认为月付<br /> |No|
| **CPU** | int | 虚拟CPU核数。可选参数：1-64（具体机型与CPU的对应关系参照控制台）。默认值: 4。 |No|
| **Memory** | int | 内存大小。单位：MB。范围 ：[1024, 262144]，取值为1024的倍数（可选范围参考控制台）。默认值：8192 |No|
| **GpuType** | string | GPU类型，枚举值["K80", "P40", "V100", "T4","T4A", "T4S","2080Ti","2080Ti-4C","1080Ti", "T4/4", "MI100", "V100S",2080","2080TiS","2080TiPro","3090","A100", "4090", "4090Pro", "4090_48G", "5090"]，MachineType为G时必填 |No|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段（可选范围与MachineType+GpuType相关） |No|
| **NetCapability** | string | 网络增强特性。枚举值：Normal，不开启;  Super，开启网络增强1.0； Ultra，开启网络增强2.0（详情参考官网文档） |No|
| **HotplugFeature** | boolean | 热升级特性。True为开启，False为未开启，默认False。 |No|
| **IsolationGroup** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |No|
| **MachineType** | string | 云主机机型（V2.0），在本字段和字段UHostType中，仅需要其中1个字段即可。枚举值["N", "C", "G", "O", "OS", "OM", "OPRO", "OMAX", "O.BM", "O.EPC"]。参考[云主机机型说明](api/uhost-api/uhost_type)。 |No|
| **MinimalCpuPlatform** | string | 最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake", "Intel/CascadelakeR", "Intel/IceLake", "Amd/Epyc2", "Amd/Auto","Ampere/Auto","Ampere/Altra"],默认值是"Intel/Auto"。 |No|
| **MaxCount** | int | 本次最大创建主机数量，取值范围是[1,100]，默认值为1。 |No|
| **Features.UNI** | boolean | 弹性网卡特性。开启了弹性网卡权限位，此特性才生效，默认 false 未开启，true 开启，仅与 NetCapability Normal 兼容。 |No|
| **SecurityMode** | string | 主机安全模式。Firewall：防火墙；SecGroup：安全组；默认值：Firewall。 |No|
| **UHostFamily** | string | 规格族。<br />由机型代号和 CPU 平台组成，用于指定云主机的硬件类型与处理器平台。<br />当 MachineType 为 "O"（快杰型）时，支持以下取值：<br />o1i：快杰型 O1 代，Intel 平台<br />o1a：快杰型 O1 代，AMD 平台<br />o1r：快杰型 O1 代，ARM 平台<br />o2i：快杰型 O2 代，Intel 平台<br />默认值：o1i 或 o1a（系统将根据资源情况自动选择）<br />当 MachineType 为 "OM"（快杰共享型）时，支持以下取值：<br />om1i：快杰内存增强型 OM1 代，Intel 平台<br />om2i：快杰内存增强型 OM2 代，Intel 平台<br />⚠️ 注意：规格族必须与 MachineType 匹配，否则请求将被拒绝。 |No|
| **MinCount** | int | 本次最小创建主机数量，取值范围是[1,100]，默认值为1。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceEnough** | boolean | 资源是否充足 |No|
| **RdmaClusterIds** | array[string] | 随机的资源对应的RdmaClusterId数组，若资源不足则为空，只有快杰系列机型，以及A800才可能有此字段 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CheckUHostResourceCapacity
&Region=yrhcTIkN
&Zone=RTUmtdBU
&ProjectId=aFwMOPWe
&ImageId=ruVbIOch
&Disks.N.IsBoot=gKJVxkeX
&Disks.N.Type=OqRcseqx
&Disks.N.Size=6
&LoginMode=OifhVpnR
&Password=PrNAnpTZ
&Name=arqiAbYy
&Tag=isFaWptf
&ChargeType=JMlYuMUL
&Quantity=2
&UHostType=hAYJSdHH
&CPU=8
&Memory=4
&GpuType=tnzkTaQe
&GPU=9
&StorageType=SiIWRbfM
&BootDiskSpace=2
&DiskSpace=3
&NetCapability=OZYggYJp
&TimemachineFeature=yes
&HotplugFeature=true
&DiskPassword=EilAQtUD
&NetworkId=RbGBaRkB
&VPCId=nJhYlNOb
&SubnetId=DjWGJOmk
&PrivateIp.N=PBlZkKsG
&PrivateMac=rGdLvUID
&SecurityGroupId=slPJvzMj
&HostType=vTqwVJAH
&InstallAgent=WXdwITJq
&ResourceType=sqWRzKIQ
&Disks.N.BackupType=HRhYZxzi
&IsolationGroup=clmfdFLB
&Disks.N.Encrypted=false
&Disks.N.KmsKeyId=nPdTWgSu
&Disks.N.CouponId=pzCdPilE
&AlarmTemplateId=1
&MachineType=ghDhssxZ
&MinimalCpuPlatform=ZwIYLzag
&MaxCount=8
&NetworkInterface.N.EIP.Bandwidth=4
&NetworkInterface.N.EIP.PayMode=jCldwuLw
&NetworkInterface.N.EIP.ShareBandwidthId=WzUVKNyc
&NetworkInterface.N.EIP.OperatorName=olWGnMJQ
&NetworkInterface.N.EIP.CouponId=jTBAXgPS
&SetId=3
&HostIp=SIRCXOSm
&NetworkInterface.N.IPv6.ShareBandwidthId=dbeXTCKs
&UserData=lvaELEkM
&Disks.N.Id=GXsgZDcp
&AutoDataDiskInit=SLfEFjiW
&NetworkInterface.N.IPv6.Address=jfKSnEKH
&CharacterName=COePftry
&PromotionId=FgbFbSsI
&ImageOsName=ONVimjaE
&PodId=PFxmFtRE
&BillActivityId=7
&BillActivityRuleId=5
&RestrictMode=UbnnCGVz
&Volumes.N.Type=iDyfOtNp
&Volumes.N.IsBoot=VOLsVJUt
&Volumes.N.Size=8
&Volumes.N.VolumeId=sRAqdPdc
&Volumes.N.CouponId=KMumcwIf
&HpcEnhanced=true
&NetworkInterface.N.CreateCernetIp=false
&KeyPairId=zuBajawQ
&Features.UNI=true
&Disks.N.BackupMode=peDmjWzg
&Disks.N.CustomBackup.Journal=ZjGVleal
&Disks.N.CustomBackup.Hour=aLrCWdGU
&Disks.N.CustomBackup.Day=EkPpEDez
&SecGroupId.N.Id=sKHFDbkJ
&SecGroupId.N.Priority=3
&SecurityMode=EDocrOUM
&UDSetId=SWidLJSg
&UDHostId=AHmYPuis
&HostBinding=true
&Disks.N.SnapshotId=pZToDOkj
&CouponId=hzEwaBBa
&MinCount=1
&UHostFamily=zezirASd
```

### 响应示例
    
```json
{
  "Action": "CheckUHostResourceCapacityResponse",
  "IPs": [
    "cdFjKkOy"
  ],
  "MountedUFSId": "twOVPrtX",
  "RdmaClusterIds": [
    "BXhwDYBZ"
  ],
  "ResourceEnough": false,
  "RetCode": 0,
  "UHostIds": [
    "rpovxuRq"
  ]
}
```





