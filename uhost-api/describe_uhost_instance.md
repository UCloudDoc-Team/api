# 获取主机信息 - DescribeUHostInstance

## 简介

获取主机或主机列表信息，并可根据数据中心，主机ID等参数进行过滤。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUHostInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUHostInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostIds.N** | string | 【数组】UHost主机的资源ID，例如UHostIds.0代表希望获取信息 的主机1，UHostIds.1代表主机2。 如果不传入，则返回当前Region 所有符合条件的UHost实例。 |No|
| **Tag** | string | 要查询的业务组名称 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **IsolationGroup** | string | 硬件隔离组id。通过硬件隔离组筛选主机。 |No|
| **VPCId** | string | vpc id。通过VPC筛选主机。北京一地域无效。 |No|
| **SubnetId** | string | 子网id。通过子网筛选主机。北京一地域无效。 |No|
| **UDiskIdForAttachment** | string | 要挂载的云盘id，过滤返回能被UDiskId挂载的云主机。目前主要针对rssd云盘使用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | UHostInstance总数 |**Yes**|
| **UHostSet** | array[[*UHostInstanceSet*](#UHostInstanceSet)] | 云主机实例列表，每项参数可见下面 UHostInstanceSet |**Yes**|

#### 数据模型


#### UHostInstanceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **IPv6Feature** | boolean | true:有ipv6特性；false，没有ipv6特性 |No|
| **UHostId** | string | UHost实例ID |No|
| **UHostType** | string | 【建议不再使用】云主机机型（旧）。参考[云主机机型说明](api/uhost-api/uhost_type)。 |No|
| **MachineType** | string | 云主机机型（新）。参考[云主机机型说明](api/uhost-api/uhost_type#主机概念20版本)。 |No|
| **CpuPlatform** | string | 云主机CPU平台。参考[云主机机型说明](api/uhost-api/uhost_type#主机概念20版本)。 |No|
| **StorageType** | string | 【建议不再使用】主机磁盘类型。 枚举值为：<br /><br /> > LocalDisk，本地磁盘; <br /><br /> > UDisk 云盘。<br /><br />只要有一块磁盘为本地盘，即返回LocalDisk。 |No|
| **ImageId** | string | 【建议不再使用】主机的系统盘ID。 |No|
| **BasicImageId** | string | 基础镜像ID（指当前自定义镜像的来源镜像） |No|
| **BasicImageName** | string | 基础镜像名称（指当前自定义镜像的来源镜像） |No|
| **Tag** | string | 业务组名称 |No|
| **Remark** | string | 备注 |No|
| **Name** | string | UHost实例名称 |No|
| **State** | string | 实例状态，枚举值：<br /><br /> >初始化: Initializing; <br /><br /> >启动中: Starting; <br /><br />> 运行中: Running; <br /><br />> 关机中: Stopping; <br /><br /> >关机: Stopped <br /><br /> >安装失败: Install Fail; <br /><br /> >重启中: Rebooting |No|
| **CreateTime** | int | 创建时间，格式为Unix时间戳 |No|
| **ChargeType** | string | 计费模式，枚举值为： Year，按年付费； Month，按月付费； Dynamic，按需付费（需开启权限）；Preemptive 为抢占式实例； |No|
| **ExpireTime** | int | 到期时间，格式为Unix时间戳 |No|
| **CPU** | int | 虚拟CPU核数，单位: 个 |No|
| **Memory** | int | 内存大小，单位: MB |No|
| **AutoRenew** | string | 是否自动续费，自动续费：“Yes”，不自动续费：“No” |No|
| **DiskSet** | array[[*UHostDiskSet*](#UHostDiskSet)] | 磁盘信息见 UHostDiskSet |No|
| **IPSet** | array[[*UHostIPSet*](#UHostIPSet)] | 详细信息见 UHostIPSet |No|
| **NetCapability** | string | 网络增强。Normal: 无；Super： 网络增强1.0； Ultra: 网络增强2.0 |No|
| **NetworkState** | string | 【建议不再使用】网络状态。 连接：Connected， 断开：NotConnected |No|
| **TimemachineFeature** | string | 【建议不再使用】数据方舟模式。枚举值：<br /><br /> > Yes: 开启方舟； <br /><br /> > no，未开启方舟 |No|
| **HotplugFeature** | boolean | true: 开启热升级； false，未开启热升级 |No|
| **SubnetType** | string | 【建议不再使用】仅北京A的云主机会返回此字段。基础网络模式：Default；子网模式：Private |No|
| **OsName** | string | 创建主机的最初来源镜像的操作系统名称（若直接通过基础镜像创建，此处返回和BasicImageName一致） |No|
| **OsType** | string | 操作系统类别。返回"Linux"或者"Windows" |No|
| **HostType** | string | 【建议不再使用】主机系列：N2，表示系列2；N1，表示系列1 |No|
| **LifeCycle** | string | 主机的生命周期类型。目前仅支持Normal：普通； |No|
| **GPU** | int | GPU个数 |No|
| **BootDiskState** | string | 系统盘状态 Normal表示初始化完成；Initializing表示在初始化。仍在初始化的系统盘无法制作镜像。 |No|
| **TotalDiskSpace** | int | 总的数据盘存储空间。 |No|
| **IsolationGroup** | string | 隔离组id，不在隔离组则返回"" |No|
| **CloudInitFeature** | boolean | true，支持cloutinit方式初始化；false,不支持 |No|
| **RdmaClusterId** | string | RDMA集群id，仅快杰云主机返回该值；其他类型云主机返回""。当云主机的此值与RSSD云盘的RdmaClusterId相同时，RSSD可以挂载到这台云主机。 |No|
| **RestrictMode** | string | 仅抢占式实例返回，LowSpeed为低速模式，PowerOff为关机模式 |No|

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
| **BackupType** | string | 备份方案。若开通了数据方舟，则为DATAARK |No|

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
| **VPCId** | string | IP地址对应的VPC ID。（北京一不支持，字段返回为空） |No|
| **SubnetId** | string | IP地址对应的子网 ID。（北京一不支持，字段返回为空） |No|
| **NetworkInterfaceId** | string | 弹性网卡为默认网卡时，返回对应的 ID 值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-02
```

### 响应示例
    
```json
{
  "Action": "DescribeUHostInstanceResponse",
  "RetCode": 0,
  "TotalCount": 1,
  "UHostSet": [
    {
      "AutoRenew": "Yes",
      "BasicImageId": "uimage-xxxx",
      "BasicImageName": "CentOS 6.6 64位",
      "BootDiskState": "Normal",
      "CPU": 2,
      "ChargeType": "Dynamic",
      "CloudInitFeature": false,
      "CpuPlatform": "Intel/Skylake",
      "CreateTime": 1583922462,
      "DiskSet": [
        {
          "DiskId": "bsi-dq2fwxoy",
          "DiskType": "CLOUD_SSD",
          "Drive": "vda",
          "Encrypted": "false",
          "IsBoot": "True",
          "Name": "系统盘_UHost",
          "Size": 20,
          "Type": "Boot"
        },
        {
          "DiskId": "bsm-pvr22btt",
          "DiskType": "CLOUD_SSD",
          "Drive": "vdb",
          "Encrypted": "false",
          "IsBoot": "False",
          "Name": "TestUDisk",
          "Size": 50,
          "Type": "Udisk"
        }
      ],
      "EncryptedDiskFeature": true,
      "ExpireTime": 1596722400,
      "GPU": 0,
      "HostType": "N3",
      "HotplugFeature": false,
      "IPSet": [
        {
          "Default": "true",
          "IP": "10.9.86.248",
          "IPMode": "IPv4",
          "Mac": "52:54:00:B1:A5:A6",
          "SubnetId": "subnet-xxxxxx",
          "Type": "Private",
          "VPCId": "uvnet-xxxxx"
        },
        {
          "Bandwidth": 1,
          "IP": "117.52.19.92",
          "IPId": "eip-xxxxxx",
          "IPMode": "IPv4",
          "Type": "BGP",
          "Weight": 50
        }
      ],
      "IPv6Feature": false,
      "ImageId": "bsi-xxxxxx",
      "IsExpire": "No",
      "IsolationGroup": "",
      "LifeCycle": "Normal",
      "MachineType": "N",
      "Memory": 2048,
      "Name": "UHost",
      "NetCapFeature": true,
      "NetCapability": "Normal",
      "NetworkState": "Connected",
      "OsName": "CentOS 6.6 64位",
      "OsType": "Linux",
      "RdmaClusterId": "",
      "Remark": "",
      "State": "Running",
      "StorageType": "UDisk",
      "SubnetType": "Default",
      "Tag": "Default",
      "TimemachineFeature": "no",
      "TotalDiskSpace": 50,
      "UHostId": "uhost-xxxxx",
      "UHostType": "N3",
      "Zone": "cn-bj2-05"
    }
  ]
}
```





