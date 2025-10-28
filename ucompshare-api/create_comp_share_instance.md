# 创建轻量级算力平台主机资源 - CreateCompShareInstance

## 简介

创建轻量级算力平台主机资源






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCompShareInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Disks.N.IsBoot** | boolean | 是否是系统盘。枚举值：<br /><br /> > True，是系统盘 <br /><br /> > False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |**Yes**|
| **Disks.N.Type** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **Disks.N.Size** | int | 磁盘大小，单位GB。请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **MachineType** | string | 云主机机型（V2.0），在本字段和字段UHostType中，仅需要其中1个字段即可。枚举值["N", "C", "G", "O", "OS", "OM", "OPRO", "OMAX", "O.BM", "O.EPC"]。参考[云主机机型说明](api/uhost-api/uhost_type)。 |**Yes**|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段（可选范围与MachineType+GpuType相关） |**Yes**|
| **Memory** | int | 内存大小。单位：MB。范围 ：[1024, 262144]，取值为1024的倍数（可选范围参考控制台）。默认值：8192 |**Yes**|
| **CPU** | int | 虚拟CPU核数。可选参数：1-64（具体机型与CPU的对应关系参照控制台）。默认值: 4。 |**Yes**|
| **GpuType** | string | GPU类型，枚举值["K80", "P40", "V100", "T4","T4A", "T4S","2080Ti","2080Ti-4C","1080Ti", "T4/4", "MI100", "V100S",2080","2080TiS","2080TiPro","3090","A100"]，MachineType为G时必填 |**Yes**|
| **CompShareImageId** | string | 镜像ID |**Yes**|
| **LoginMode** | string | 主机登陆模式。密码（默认选项）: Password |No|
| **ChargeType** | string | 计费模式。枚举值为: <br /><br /> > Month，按月付费；<br /><br /> > Day，按天付费；<br /><br /> > Dynamic，按小时预付费 <br /><br /> > Postpay，按小时后付费（支持关机不收费，目前仅部分可用区支持，请联系您的客户经理） <br /><br /> > Spot计费为抢占式实例(内测阶段) <br /><br /> 默认为月付 |No|
| **Quantity** | int | 购买时长。默认:值 1。按小时购买（Dynamic/Postpay）时无需此参数。 月付时，此参数传0，代表购买至月末。 |No|
| **MinimalCpuPlatform** | string | 最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake", "Intel/CascadelakeR", "Intel/IceLake", "Amd/Epyc2", "Amd/Auto","Ampere/Auto","Ampere/Altra"],默认值是"Intel/Auto"。 |No|
| **Password** | string | UHost密码。请遵照[字段规范](api/uhost-api/specification)设定密码。密码需使用base64进行编码，举例如下：# echo -n Password1 \| base64UGFzc3dvcmQx。 |No|
| **Name** | string | 实例名称 |No|
| **SecurityGroupId** | string | 防火墙Id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UHostIds** | array[string] | UHost实例Id集合 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCompShareInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=lnUhAYpT
&ImageId=KSuPKTtW
&LoginMode=dnnfRljU
&Disks.N.IsBoot=true
&Disks.N.Type=ptHJPOco
&Disks.N.Size=5
&MachineType=iyENElDv
&GPUType=pzRkInee
&GPU=VkyjzhQy
&ChargeType=USDhlfAP
&Quantity=7
&MinimalCpuPlatform=QErLvHVg
&Memory=1
&MaxCount=6
&Password=UwOdhzOu
&CPU=1
&Name=ACsfjhFW
&SecurityGroupId=DhXQhVSq
```

### 响应示例
    
```json
{
  "Action": "CreateCompShareInstanceResponse",
  "IPs": [
    "hhySlhCv"
  ],
  "RetCode": 0,
  "UHostIds": [
    "NIdfqvRv"
  ]
}
```





