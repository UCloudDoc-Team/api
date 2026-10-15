# 集群增加伸缩组V2 - AddUK8SAutoScalingGroupV2

## 简介

集群增加伸缩组V2









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUK8SAutoScalingGroupV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |**Yes**|
| **ProjectId** | string | 项目ID |No|
| **Region** | string | 地域 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|
| **Name** | string | 伸缩组名字 |**Yes**|
| **CPU** | int | 节点CPU大小 |**Yes**|
| **Mem** | int | 节点Mem大小 |**Yes**|
| **MachineType** | string | 【新增】云主机机型（V2.0），枚举值["N", "C", "G"]。 |**Yes**|
| **Password** | string | 节点密码,不填为随机 |No|
| **BootDiskType** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **DataDiskType** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **DataDiskSize** | int | 数据磁盘大小，单位GB。默认0。范围 ：[20, 1000] |No|
| **MinmalCpuPlatform** | string | 最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"。 |No|
| **GpuType** | string | GPU类型，枚举值["K80", "P40", "V100"] |No|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段 |No|
| **Labels** | string | key=value,多组用”,“隔开，最多5组 |No|
| **MaxPods** | int | 默认110, 支持16-512 |No|
| **Min** | int | 伸缩组最小节点数 |No|
| **Max** | int | 伸缩组最大节点数 |No|
| **BootDiskSize** | int | 系统盘大小，单位GB。默认40。范围：[40, 500]。注意SSD本地盘无法调整。 |No|
| **ImageId** | string | 镜像 Id，不填时后台程序会自动选用一个可用的镜像 Id，不支持用户自定义镜像，传入自定义镜像 Id 将报错 |No|
| **UserData** | string | cloud-init 初始化使用的 UserData |No|
| **InitScript** | string | uk8s 部署完成后执行的用户脚本 |No|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Dynamic，按小时预付费 <br /><br /> > Postpay，按小时后付费（支持关机不收费，目前仅部分可用区支持，请联系您的客户经理） <br /><br />Preemptive计费为抢占式实例 <br /><br /> 默认为按小时预付费 |No|
| **IsolationGroup** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |No|
| **Taints** | string | Node节点污点，形式为key=value:effect，多组taints用”,“隔开,最多支持五组。 |No|
| **Tag** | string | 业务组 |No|
| **Priority** | int | 伸缩组的优先级，取值[1, 100]，数值越大优先级越高，在扩容的时候会被更优先考虑。 |No|
| **NodeGroupId** | string | 伸缩组绑定的节点池id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Id** | string | 伸缩组ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUK8SAutoScalingGroupV2
&Zone=vNFthxBl
&ProjectId=bvukNjaZ
&Region=KVccZqEg
&ClusterId=fIabqPCy
&CPU=9
&Count=8
&Password=urXocMHq
&Mem=1
&ChargeType=izxhCiKo
&BootDiskType=FxfDciLu
&DataDiskType=CiMXvwAm
&DataDiskSize=XBRksLzX
&Quantity=8
&MachineType=qkXyGuCU
&MinmalCpuPlatform=eQNDWrsb
&GpuType=qRAjUKWD
&GPU=3
&Labels=BbnsxaIO
&MaxPods=6
&IsolationGroup=RKVIlUII
&Min=uhQfZvVV
&Max=tFexHdvz
&Name=XaMCyArc
&ImageId=lNVOxsKn
&UserData=eSsxLuhI
&InitScript=VXJApjOH
&ChargeType=WQAZJFaZ
&IsolationGroup=qnQEekWT
&ChargeType=WULQCDuJ
&IsolationGroup=EKdDYzEZ
&Taints=ZvKOORev
&Tag=ZhXzQaMc
&BootDiskSize=8
&Priority=3
&NodeGroupId=ShEQvKMF
```

### 响应示例
    
```json
{
  "Action": "AddUK8SAutoScalingGroupV2Response",
  "Id": "yoeiVSWn",
  "Message": "LxKsbaPZ",
  "RetCode": 0
}
```





