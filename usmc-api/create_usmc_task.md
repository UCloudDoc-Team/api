# 创建USMC任务 - CreateUSMCTask

## 简介

创建USMC任务









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUSMCTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 任务名称，长度不能超过 128 |**Yes**|
| **AgentId** | string | 客户端ID |**Yes**|
| **TargetRegion** | string | 目标地域 |**Yes**|
| **TargetZone** | string | 目标可用区 |**Yes**|
| **TargetVPCId** | string | 目标VPCId, 默认为default |**Yes**|
| **TargetSubnetId** | string | 目标子网 ID, 默认为default |**Yes**|
| **PlanId** | string | 迁移计划ID |**Yes**|
| **TargetUHostPassword** | string | 目标机器密码 |**Yes**|
| **Incremental** | string | 是否开启自动增量， 默认关闭 ture/false |No|
| **Interval** | string | 当Incremental为true时， 指定增量同步间隔，单位分钟 |No|
| **BandwidthLimit** | string | 设置的最大的速率，单位MB/s，公网/专线(0, 56]，用户网(0, 1024]，不填/超过默认是峰值 |No|
| **MachineType** | string | 机型 |No|
| **MinimalCpuPlatform** | string | cpu平台 |No|
| **EIPOperatorName** | string |  [若绑定EIP，此参数必填] 弹性IP的线路。枚举值:国际: International BGP: Bgp |No|
| **EIPBandwidth** | string | eip带宽 |No|
| **EIPPayMode** | string | 弹性IP带宽, 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. "Free":免费带宽模式.默认为 "Bandwidth" |No|
| **EIPShareBandwidthId** | string | 绑定的共享带宽Id, 仅当PayMode为ShareBandwidth时有效 |No|
| **DataDiskType** | string | 数据盘类型，枚举值与磁盘类型相同。不指定时使用系统盘类型 |No|
| **Gpu** | int | GPU卡核心数。仅GPU机型支持此字段（可选范围与MachineType+GpuType相关） |No|
| **GpuType** | string | GPU类型，枚举值["K80", "P40", "V100", "T4","T4A", "T4S","2080Ti","2080Ti-4C","1080Ti", "T4/4", "MI100", "V100S",2080","2080TiS","2080TiPro","3090","A100"]，MachineType为G时必填 |No|
| **Cpu** | int | 虚拟CPU核数。默认值为源主机核数 |No|
| **Memory** | int | 内存大小。单位：MB。默认值为源机器内存大小 |No|
| **UDSetId** | string | 【私有专区属性】专区ID |No|
| **UDHostId** | string | 【私有专区属性】专区宿主机id |No|
| **HostBinding** | boolean | 【私有专区属性】专区云主机开启宿住关联属性 |No|
| **TargetUHostChargeType** | string | 目标机器收费类型，值可以是 Year,Month,Dynamic， 默认为 Dynamic |No|
| **TargetUHostQuantity** | string | 目标机器收费周期，默认为 1，StopOverHostChargeType 为 Month 时可以为 0 |No|
| **TargetUHostPrivateIp** | string | 目标机器内网ip |No|
| **SystemDiskType** | string | 系统盘类型，枚举值:"CLOUD_RSSD",RSSD云盘;"CLOUD_SSD",SSD云盘。默认为CLOUD_RSSD |No|
| **SecGroupId.N.Id** | string | 安全组 ID。至多可以同时绑定5个安全组。 |No|
| **SecGroupId.N.Priority** | string | 安全组优先级。取值范围[1, 5] |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | object | CreateUSMCTaskResData  |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUSMCTask
&Name=RiTNTfPv
&AgentId=fEKYvBcp
&TargetRegion=XupsFLht
&TargetZone=ZXRhmlcT
&Incremental=wkKiRedm
&Interval=zAZwpcgP
&BandwidthLimit=YmwhOkfL
&TargetVPCId=WiLHvNbH
&TargetSubnetId=gxWleKNJ
&ProjectId=KEmOYzUb
&SetId=YXXrRIpv
&StopOverHostChargeType=YplVJDmC
&StopOverHostQuantity=qnyKulrZ
&IP=khlqvxqf
&Password=CtImCWpC
&EIPOperatorName=etdVEuxt
&EIPBandwidth=CpvCFxDZ
&EIPPayMode=KlvWQjQH
&EIPShareBandwidthId=WlhDIMqw
&TargetHostname=SquOMcbU
&TargetHostname=IIrTEUPs
&TargetHostname=qTdShCoy
&MachineType=bSqxEHWD
&MinimalCpuPlatform=vWearvLt
&MachineType=GhydOYic
&MinimalCpuPlatform=iPNPxFpm
&DiskType=iNHVCuhG
&Gpu=4
&GpuType=SaiFhPSB
&Cpu=4
&Memory=8
&UDSetId=RYiqXUdz
&UDHostId=XsryFEbR
&HostBinding=true
&DataDiskType=MNZBGIFr
&UDSetId=EeCiGrUv
&UDHostId=oQVGkXlz
&HostBinding=false
&SecGroupId.N.Id=IFAkhyeu
&SecGroupId.N.Priority=FRNcCBTn
```

### 响应示例
    
```json
{
  "Action": "CreateUSMCTaskResponse",
  "Data": {},
  "Message": "aJpSfwDp",
  "RetCode": 0
}
```





