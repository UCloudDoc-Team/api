# 获取用户所有地域的主机资源列表 - DescribeCompShareInstance

## 简介

获取用户所有地域下主机资源信息列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCompShareInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostIds.N** | string | 【数组】UHost主机的资源ID，例如UHostIds.0代表希望获取信息 的主机1，UHostIds.1代表主机2。 如果不传入，则返回当前Region 所有符合条件的UHost实例。 |No|
| **WithoutGpu** | boolean | 无卡GPU |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | UHostInstance总数 |**Yes**|
| **UHostSet** | array[[*CompShareInstanceSet*](#CompShareInstanceSet)] | 云主机实例列表，每项参数可见下面 UHostInstanceSet |**Yes**|

#### 数据模型


#### CompShareInstanceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **StopSchedulerTime** | int | 计划关机时间 |No|
| **UHostId** | string | 实例Id |No|
| **MachineType** | string | 机型信息 |No|
| **CpuPlatform** | string | CPU平台。如"Intel/Auto"、"Amd/Auto"等等 |No|
| **CompShareImageId** | string | 镜像Id |No|
| **CompShareImageName** | string | 镜像名称 |No|
| **CompShareImageOwnerAlias** | string | 镜像来源 |No|
| **CompShareImageBillId** | string | 用于镜像计费的Id |No|
| **CompShareImageStatus** | string | 镜像状态 |No|
| **CompShareImageType** | string | 镜像类型<br />- System 系统镜像<br />- App 应用镜像<br />- Custom 自制镜像<br />- Community 社区镜像 |No|
| **InstanceType** | string | 实例类型。"UHost": 普通主机；"Container": 容器主机 |No|
| **Password** | string | 主机密码。由Base64编码 |No|
| **SshLoginCommand** | string | SSH登录命令 |No|
| **Name** | string | 实例名称 |No|
| **Tag** | string | 实例业务组 |No|
| **Remark** | string | 实例备注 |No|
| **State** | string | 实例状态，枚举值：<br /><br /> >初始化: Initializing; <br /><br /> >启动中: Starting; <br /><br />> 运行中: Running; <br /><br />> 关机中: Stopping; <br /><br /> >关机: Stopped <br /><br /> >安装失败: Install Fail; <br /><br /> >重启中: Rebooting; <br /><br /> >升级改配中: Resizing; <br /><br /> > 未知(空字符串，获取状态超时或出错)： |No|
| **ChargeType** | string | 计费模式，枚举值为： Year，按年付费； Month，按月付费； Dynamic，按时付费；Postpay，按需付费 |No|
| **CPU** | int | 虚拟CPU核数，单位: 个 |No|
| **Memory** | int | 内存大小，单位：MB |No|
| **GpuType** | string | GPU类型。如: "4090" |No|
| **GPU** | int | GPU个数 |No|
| **GraphicsMemory** | [*GraphicsMemory*](#GraphicsMemory) | GPU显存信息 |No|
| **AutoRenew** | string | 是否自动续费，自动续费：“Yes”，不自动续费：“No” |No|
| **IsExpire** | string | 是否过期。Yes：已过期；No：未过期 |No|
| **OsName** | string | 虚机镜像的名称 |No|
| **OsType** | string | 虚机镜像操作系统类型。"Linux"<br />"Windows" |No|
| **TotalDiskSpace** | int | 总的数据盘存储空间 |No|
| **CpuArch** | string | CPU架构。"x86_64"/"i386"等 |No|
| **DiskSet** | array[[*UHostDiskSet*](#UHostDiskSet)] | 详情见UHostDiskSet |No|
| **IPSet** | array[[*UHostIPSet*](#UHostIPSet)] | 详情见UHostIPSet |No|
| **Softwares** | array[[*SoftwareAddr*](#SoftwareAddr)] | 软件地址 |No|
| **InstancePrice** | float | 主机价格 |No|
| **CompShareImagePrice** | float | 镜像价格 |No|
| **ExpireTime** | int | 过期时间 |No|
| **CreateTime** | int | 创建时间 |No|
| **SupportWithoutGpuStart** | boolean | 此实例是否支持无卡开机 |No|
| **WithoutGpuSpec** | [*WithoutGpuSpec*](#WithoutGpuSpec) | 无卡配置规格，详情见：WithoutGpuSpecInfo |No|
| **StopTime** | int | 定时关机时间 |No|
| **UpdateTime** | int | 虚机状态更新时间 |No|
| **ReleaseTime** | int | 释放时间（关机时候返回） |No|
| **DiskPriceInfo** | array[[*DiskPriceInfo*](#DiskPriceInfo)] | 磁盘价格信息，详见:DiskPriceInfo |No|
| **PostPayPowerOffBillingResource** | array[[*DiskPriceInfo*](#DiskPriceInfo)] | 后付费关机计费信息列表，详见：详见:DiskPriceInfo |No|
| **MonitorMessages** | [*MonitorMessage*](#MonitorMessage) | 监控信息，详见：MonitorMessage |No|

#### GraphicsMemory

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Value** | int | 值，单位是GB |No|
| **Rate** | int | 交互展示参数，可忽略 |No|

#### UHostDiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskType** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **IsBoot** | string | 是否是系统盘。枚举值：<br /><br /> > True，是系统盘 <br /><br /> > False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |**Yes**|
| **Encrypted** | string | "true": 加密盘 "false"：非加密盘 |No|
| **Type** | string | 【建议不再使用】磁盘类型。系统盘: Boot，数据盘: Data,网络盘：Udisk |No|
| **DiskId** | string | 磁盘ID |No|
| **Name** | string | UDisk名字（仅当磁盘是UDisk时返回） |No|
| **Drive** | string | 磁盘盘符 |No|
| **Size** | int | 磁盘大小，单位: GB |No|

#### UHostIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IPMode** | string | IPv4/IPv6； |**Yes**|
| **Default** | string | 内网 Private 类型下，表示是否为默认网卡。true: 是默认网卡；其他值：不是。 |No|
| **Mac** | string | 内网 Private 类型下，当前网卡的Mac。 |No|
| **Weight** | int | 当前EIP的权重。权重最大的为当前的出口IP。 |No|
| **Type** | string | 国际: Internation，BGP: Bgp，内网: Private |No|
| **IPId** | string | 外网IP资源ID 。(内网IP无对应的资源ID) |No|
| **IP** | string | IP地址 |No|
| **Bandwidth** | int | IP对应的带宽, 单位: Mb  (内网IP不显示带宽信息) |No|
| **VPCId** | string | IP地址对应的VPC ID。（华北（北京）不支持，字段返回为空） |No|
| **SubnetId** | string | IP地址对应的子网 ID。（华北（北京）不支持，字段返回为空） |No|
| **NetworkInterfaceId** | string | 弹性网卡为默认网卡时，返回对应的 ID 值 |No|

#### SoftwareAddr

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 软件名称 |No|
| **URL** | string | 软件地址 |No|

#### WithoutGpuSpec

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Cpu** | int | cpu |No|
| **Memory** | int | 内存 |No|
| **Gpu** | int | gpu |No|

#### DiskPriceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型 |No|
| **Price** | float | 磁盘价格 |No|
| **IsBoot** | boolean | 是否为系统盘 |No|

#### MonitorMessage

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CpuUsageRate** | string | CPU使用率 |No|
| **MemUsageRate** | string | 内存使用率 |No|
| **GpuInfo** | array[[*GpuMonitorInfo*](#GpuMonitorInfo)] | GPU卡监控信息 |No|

#### GpuMonitorInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GpuUsageRate** | string | GPU卡使用率 |No|
| **MemoryUsageRate** | string | GPU显存使用率 |No|
| **GPU** | string | GPU卡名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCompShareInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=IoMVpdoj
&UHostIds.N=cnHQCXgZ
&Tag=iDnowauu
&Offset=2
&Limit=9
&VPCId=YVTTNJzc
&SubnetId=xsDQoSws
&NoEIP=false
&ResourceType=zFIXncgL
&UDiskIdForAttachment=true
&WithoutGpu=false
```

### 响应示例
    
```json
{
  "Action": "DescribeCompShareInstanceResponse",
  "RetCode": 0,
  "TotalCount": 8,
  "UHostSet": [
    {
      "AutoRenew": "KHTdKhxO",
      "BasicImageId": "AFGqwjpj",
      "BasicImageName": "fFSjyQry",
      "BootDiskState": "wfcQeKzE",
      "CPU": 5,
      "ChargeType": "xePQZDOs",
      "CloudInitFeature": false,
      "CpuPlatform": "aKtmIaxl",
      "CreateTime": 7,
      "EpcInstance": true,
      "ExpireTime": 4,
      "GPU": 1,
      "GpuType": "syCegFMi",
      "HiddenKvm": false,
      "HostType": "jpATaXsk",
      "HotPlugMaxCpu": 8,
      "HotplugFeature": false,
      "HpcFeature": true,
      "IPSet": [
        {
          "Bandwidth": 8,
          "Default": "tgnSjelJ",
          "IP": "ZmBtTbhB",
          "IPId": "subuipxK",
          "IPMode": "UulHwAYv",
          "Mac": "ACuDMaqD",
          "NetworkInterfaceId": "FauzdzHm",
          "SubnetId": "SYfTyiiN",
          "Type": "XtwAFLux",
          "VPCId": "ASpSKtze",
          "Weight": 8
        }
      ],
      "IPv6Feature": false,
      "ImageId": "rOLrvehW",
      "IsolationGroup": "dMNyStGT",
      "KeyPair": {},
      "LifeCycle": "SwXCLmkq",
      "MachineType": "IqVoJXvL",
      "Memory": 6,
      "Name": "pkIdkUfV",
      "NetCapability": "kTFrfCiG",
      "NetworkState": "FcaxZMik",
      "OsName": "gMqlgBlI",
      "OsType": "uTGzcPdd",
      "RdmaClusterId": "ncMkxiOT",
      "Remark": "zATjHVlb",
      "RestrictMode": "VTendLlO",
      "SecGroupInstance": false,
      "SpotAttribute": {},
      "State": "TnNuGSYE",
      "StorageType": "FEFUzaYx",
      "SubnetType": "sDBMGbYE",
      "Tag": "MHPHAgpt",
      "TimemachineFeature": "GiqxwKDZ",
      "TotalDiskSpace": 6,
      "UDHostAttribute": {},
      "UHostId": "wMwHWPOr",
      "UHostType": "NwCllZUf",
      "Zone": "xdLgDoph"
    }
  ]
}
```





