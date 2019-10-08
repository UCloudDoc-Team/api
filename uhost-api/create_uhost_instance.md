# 创建云主机-CreateUHostInstance

创建UHost实例。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ImageId|string|镜像ID。 请通过 [DescribeImage](describe_image.html)获取|**Yes**|
|Password|string|UHost密码。请遵照[[api:uhost-api:specification|字段规范]]设定密码。密码需使用base64进行编码，举例如下：# echo -n Password1 | base64UGFzc3dvcmQx。|**Yes**|
|Disks.N.IsBoot|string|是否是系统盘。枚举值：\\ > True，是系统盘 \\ > False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。|**Yes**|
|Disks.N.Type|string|磁盘类型。请参考[[api:uhost-api:disk_type|磁盘类型]]。|**Yes**|
|Disks.N.Size|int|磁盘大小，单位GB。请参考[[api:uhost-api:disk_type|磁盘类型]]。|**Yes**|
|LoginMode|string|主机登陆模式。密码（默认选项）: Password。|**Yes**|
|Name|string|UHost实例名称。默认：UHost。请遵照[[api:uhost-api:specification|字段规范]]设定实例名称。|No|
|Tag|string|业务组。默认：Default（Default即为未分组）。请遵照[[api:uhost-api:specification|字段规范]]设定业务组。|No|
|ChargeType|string|计费模式。枚举值为： \\ > Year，按年付费； \\ > Month，按月付费；\\ > Dynamic，按小时付费 \\ 默认为月付|No|
|Quantity|int|购买时长。默认:值 1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传0，代表购买至月末。|No|
|UHostType|string|【建议后续不再使用】云主机机型V1.0。参考[[api:uhost-api:uhost_type|云主机机型说明]]。|No|
|CPU|int|虚拟CPU核数。可选参数：1-64（具体机型与CPU的对应关系参照控制台）。默认值: 4。|No|
|Memory|int|内存大小。单位：MB。范围 ：[1024, 262144]，取值为1024的倍数（可选范围参考控制台）。默认值：8192|No|
|GpuType|string|GPU类型，枚举值["K80", "P40", "V100"]|No|
|GPU|int|GPU卡核心数。仅GPU机型支持此字段（可选范围与UHostType相关）|No|
|KeyPair|string|【暂不支持】Keypair公钥，LoginMode为KeyPair时此项必须|No|
|StorageType|string|【待废弃，不建议调用】磁盘类型，同时设定系统盘和数据盘的磁盘类型。枚举值为：LocalDisk，本地磁盘; UDisk，云硬盘；默认为LocalDisk。仅部分可用区支持云硬盘方式的主机存储方式，具体请查询控制台。|No|
|BootDiskSpace|int|【待废弃，不建议调用】系统盘大小。 单位：GB， 范围[20,100]， 步长：10|No|
|DiskSpace|int|【待废弃，不建议调用】数据盘大小。 单位：GB， 范围[0,8000]， 步长：10， 默认值：20，云盘支持0-8000；本地普通盘支持0-2000；本地SSD盘（包括所有GPU机型）支持100-1000|No|
|NetCapability|string|网络增强。枚举值：Normal（默认），不开启;  Super，开启网络增强1.0； Ultra，开启网络增强2.0（仅支持部分可用区，请参考控制台）|No|
|TimemachineFeature|string|【待废弃，不建议调用】是否开启方舟特性。Yes为开启方舟，No为关闭方舟。目前仅选择普通本地盘+普通本地盘 或 SSD云盘+普通云盘的组合支持开启方舟。|No|
|HotplugFeature|bool|是否开启热升级特性。True为开启，False为未开启，默认False。|No|
|DiskPassword|string|【待废弃，不建议调用】加密盘的密码。若输入此字段，自动选择加密盘。加密盘需要权限位。|No|
|NetworkId|string|【已废弃】网络ID（VPC2.0情况下无需填写）。VPC1.0情况下，若不填写，代表优先选择基础网络； 若填写，代表选择子网。参见DescribeSubnet。|No|
|VPCId|string|VPC ID。默认为当前地域的默认VPC。|No|
|SubnetId|string|子网 ID。默认为当前地域的默认子网。|No|
|PrivateIp.N|string|【数组】创建云主机时指定内网IP。若不传值，则随机分配当前子网下的IP。调用方式举例：PrivateIp.0=x.x.x.x。当前只支持一个内网IP。|No|
|PrivateMac|string|【批量创建该参数无效】【内部字段】创建云主机时指定Mac。调用方式举例：PrivateMac="xx:xx:xx:xx:xx:xx"。|No|
|SecurityGroupId|string|防火墙Id，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeSecurityGroup](../unet-api/describe_security_group.html)。|No|
|UserDataScript|string|【暂不支持】cloudinit方式下，用户初始化脚本|No|
|HostType|string|【已废弃】宿主机类型，N2，N1|No|
|InstallAgent|string|【暂不支持】是否安装UGA。'yes': 安装；其他或者不填：不安装。|No|
|ResourceType|int|【内部参数】资源类型|No|
|Disks.N.BackupType|string|磁盘备份方案。枚举值：\\ > NONE，无备份 \\ > DATAARK，数据方舟 \\ 当前磁盘支持的备份模式参考 [[api:uhost-api:disk_type|磁盘类型]]|No|
|IsolationGroup|string|硬件隔离组id。可通过DescribeIsolationGroup获取。|No|
|Disks.N.Encrypted|bool|【功能仅部分可用区开放，详询技术支持】磁盘是否加密。加密：true, 不加密: false加密必须传入对应的的KmsKeyId|No|
|Disks.N.KmsKeyId|string|【功能仅部分可用区开放，详询技术支持】kms key id。选择加密盘时必填。|No|
|Disks.N.CouponId|string|云盘代金券id。不适用于系统盘/本地盘。请通过DescribeCoupon接口查询，或登录用户中心查看|No|
|AlarmTemplateId|int|告警模板id，如果传了告警模板id，且告警模板id正确，则绑定告警模板。绑定告警模板失败只会在后台有日志，不会影响创建主机流程，也不会在前端报错。|No|
|MinimalCpuPlatform|string|最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"。|No|
|MachineType|string|云主机机型（V2.0），枚举值["N", "C", "G", "O"]。参考[[api:uhost-api:uhost_type|云主机机型说明]]。|No|
|MaxCount|int|【批量创建主机时必填】最大创建主机数量，取值范围是[1,100];|No|
|NetworkInterface.N.EIP.Bandwidth|int|【如果绑定EIP这个参数必填】弹性IP的外网带宽, 单位为Mbps. 共享带宽模式必须指定0M带宽, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-300]，带宽计费[1-800]|No|
|NetworkInterface.N.EIP.PayMode|string|弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. "Free":免费带宽模式.默认为 "Bandwidth".|No|
|NetworkInterface.N.EIP.ShareBandwidthId|string|绑定的共享带宽Id，仅当PayMode为ShareBandwidth时有效|No|
|NetworkInterface.N.EIP.GlobalSSH.Area|string|填写支持SSH访问IP的地区名称，如“洛杉矶”，“新加坡”，“香港”，“东京”，“华盛顿”，“法兰克福”。Area和AreaCode两者必填一个|No|
|NetworkInterface.N.EIP.OperatorName|string|【如果绑定EIP这个参数必填】弹性IP的线路如下: 国际: International BGP: Bgp 各地域允许的线路参数如下: cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International kr-seoul:International us-ws:International ge-fra:International sg:International tw-kh:International.其他海外线路均为 International|No|
|NetworkInterface.N.EIP.GlobalSSH.Port|int|SSH端口，1-65535且不能使用80，443端口|No|
|NetworkInterface.N.EIP.CouponId|string|当前EIP代金券id。请通过DescribeCoupon接口查询，或登录用户中心查看|No|
|NetworkInterface.N.EIP.GlobalSSH.AreaCode|string|GlobalSSH的。AreaCode, 区域航空港国际通用代码。Area和AreaCode两者必填一个|No|
|SetId|int||No|
|CouponId|string|主机代金券ID。请通过DescribeCoupon接口查询，或登录用户中心查看|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UHostIds|array|UHost实例Id集合|No|
|IPs|array|【批量创建不会返回】IP信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ImageId=uimage-xxxx
&Password=xxx
&MinimalCPUPlatform=Intel/Auto
&MachineType=N
&CPU=1
&Memory=1024
&Disks.0.Type=CLOUD_SSD
&Disks.0.IsBoot=True
&Disks.0.Size=20
&Disks.1.Type=CLOUD_NORMAL
&Disks.1.IsBoot=False
&Disks.1.Size=100
&MaxCount=8
&NetworkInterface.0.EIP.OperatorName=Bgp
&NetworkInterface.0.EIP.Bandwidth=2
&NetworkInterface.0.EIP.PayMode=Bandwidth
```

# Response Example
```
{
    "Action": "CreateUHostInstanceResponse", 
    "IPs": [
        "10.19.xx.xxx"
    ], 
    "RetCode": 0, 
    "UHostIds": [
        "uhost-xxx"
    ]
}
```

