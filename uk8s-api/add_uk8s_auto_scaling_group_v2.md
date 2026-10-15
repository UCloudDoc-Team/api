# 集群增加伸缩组V2 - AddUK8SAutoScalingGroupV2

## 简介

创建绑定已有节点池的自动伸缩组。当前请求校验仍要求提供 CPU、Mem、MachineType 和 Zone。









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
| **MachineType** | string | 云主机机型。该参数仍需传入；实际节点规格取自绑定的节点池。 |**Yes**|
| **Min** | int | 最小节点数，范围 0–100，且不得大于 Max。必须显式传入，允许为 0。 |**Yes**|
| **Max** | int | 最大节点数，范围 1–100，且不得小于 Min。 |**Yes**|
| **NodeGroupId** | string | 伸缩组绑定的有效节点池 ID。当前实现必须提供，节点配置取自该节点池。 |**Yes**|
| **Password** | string | Base64 编码的节点登录密码。LoginMode 为 Password（默认）时必填，不会自动生成随机密码；KeyPair 模式下可不填。 |No|
| **BootDiskType** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **DataDiskType** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。默认为SSD云盘 |No|
| **DataDiskSize** | int | 数据磁盘大小，单位GB。默认0。范围 ：[20, 1000] |No|
| **MinmalCpuPlatform** | string | 最低 CPU 平台的兼容字段；同时提供 MinimalCpuPlatform 时以其为准。 |No|
| **GpuType** | string | GPU 类型；实际节点规格取自绑定的节点池。 |No|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段 |No|
| **Labels** | string | key=value,多组用”,“隔开，最多5组 |No|
| **MaxPods** | int | 默认110, 支持16-512 |No|
| **BootDiskSize** | int | 系统盘大小，单位GB。默认40。范围：[40, 500]。注意SSD本地盘无法调整。 |No|
| **ImageId** | string | 镜像 Id，不填时后台程序会自动选用一个可用的镜像 Id，不支持用户自定义镜像，传入自定义镜像 Id 将报错 |No|
| **UserData** | string | Base64 编码的 cloud-init 用户数据。 |No|
| **InitScript** | string | Base64 编码的用户脚本，在 UK8S 节点初始化完成后执行。 |No|
| **ChargeType** | string | 计费模式：Year、Month、Dynamic、Postpay，默认 Dynamic。此接口不接受 Preemptive。 |No|
| **IsolationGroup** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |No|
| **Taints** | string | Node节点污点，形式为key=value:effect，多组taints用”,“隔开,最多支持五组。 |No|
| **Tag** | string | 业务组 |No|
| **Priority** | int | 伸缩组的优先级，取值[1, 100]，数值越大优先级越高，在扩容的时候会被更优先考虑。 |No|
| **LoginMode** | string | 节点登录方式：Password 或 KeyPair，默认 Password。 |No|
| **KeyPairId** | string | 登录密钥对 ID。LoginMode 为 KeyPair 时必填。 |No|
| **MinimalCpuPlatform** | string | 最低 CPU 平台；优先于兼容字段 MinmalCpuPlatform。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AsgId** | string | 创建的伸缩组 ID。 |No|




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
&LoginMode=wvTwlPWn
&KeyPairId=cDTkQwLg
&MinimalCpuPlatform=eiNmBuWe
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





