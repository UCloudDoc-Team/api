# 添加Node节点（物理云主机） - AddUK8SPHostNode

## 简介

为UK8S集群添加一台或多台物理云主机类型的节点。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUK8SPHostNode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ClusterId** | string | UK8S集群ID。 可从UK8S控制台获取。 |**Yes**|
| **Count** | int | 最大创建Node节点数量，取值范围是[1,10]。 |**Yes**|
| **Password** | string | Node节点密码。请遵照[字段规范](api/uhost-api/specification)设定密码。密码需使用base64进行编码，如下：# echo -n Password1 \| base64 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> 默认为月付 |**Yes**|
| **Quantity** | int | 购买时长。默认: 1。月付时，此参数传0，代表了购买至月末。 |No|
| **Labels** | string | Node节点标签。key=value形式,多组用”,“隔开，最多5组。 如env=pro,type=game |No|
| **MaxPods** | int | 默认110，生产环境建议小于等于110。 |No|
| **Type** | string | 物理机类型，默认为：db-2(基础型-SAS-V3) |No|
| **Raid** | string | Raid配置，默认Raid10 支持:Raid0、Raid1、Raid5、Raid10，NoRaid |No|
| **NIC** | string | 网络环境，可选千兆：1G ，万兆：10G， 默认1G。 |No|
| **SubnetId** | string | 子网 ID。默认为集群创建时填写的子网ID，也可以填写集群同VPC内的子网ID。 |No|
| **ImageId** | string | 镜像 Id，不填时后台程序会自动选用一个可用的镜像 Id，支持用户自定义镜像，自定义镜像必须基于基础镜像制作。 |No|
| **DisableSchedule** | boolean | 用于标示添加完节点后是否将节点临时禁用. 传入 "true" 表示禁用,传入其它或不传表示不禁用 |No|
| **InitScript** | string | 用户自定义Shell脚本。与UserData的区别在于InitScript在节点初始化完毕后才执行。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUK8SPHostNode
&Zone=mASwhOwS
&ProjectId=TtFuuCvl
&Region=ephfLtkg
&ClusterId=gCCKbTeA
&CPU=7
&Count=3
&Password=UiYvduOo
&Mem=2
&ChargeType=wmcAhsnG
&BootDiskType=zmNhZzRf
&DataDiskType=GKVjMCWI
&DataDiskSize=fAJBjatE
&Quantity=8
&MachineType=hYudGdxE
&MinmalCpuPlatform=pXPBzsJd
&GpuType=ilPxSGRq
&GPU=9
&Labels=JUQASjlI
&Kubelet.MaxPods=1
&Type=qxQEPxPH
&Raid=ypSBWSeV
&NIC=gzqVBNpS
&Type=fTtSpRXy
&Raid=iUVCnclz
&NIC=YctuhWeH
&SubnetId=VlAVQbbb
&ImageId=LQuioHZk
&DisableSchedule=jEVHAJOV
&InitScript=LzBmCbai
```

### 响应示例
    
```json
{
  "Action": "AddUK8SPHostNodeResponse",
  "Message": "ovAEHXng",
  "RetCode": 0
}
```





