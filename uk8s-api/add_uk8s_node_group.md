# 添加UK8S节点池 - AddUK8SNodeGroup

## 简介

添加UK8S节点池









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUK8SNodeGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NodeGroupName** | string | 节点池名字 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|
| **ImageId** | string | 镜像ID |No|
| **MachineType** | string | 云主机机型。枚举值["N", "C", "G", "O", "OS"]。参考[云主机机型说明](api/uhost-api/uhost_type)。 |No|
| **MinimalCpuPlatform** | string | 最低cpu平台，枚举值["Intel/Auto", "Intel/IvyBridge", "Intel/Haswell", "Intel/Broadwell", "Intel/Skylake", "Intel/Cascadelake"；"Intel/CascadelakeR"; “Amd/Epyc2”,"Amd/Auto"],默认值是"Intel/Auto" |No|
| **CPU** | int | GPU卡核心数。仅GPU机型支持此字段（可选范围与MachineType+GpuType相关） |No|
| **Mem** | int | 内存大小。单位：MB |No|
| **GpuType** | string | GPU类型 |No|
| **GPU** | int | GPU卡核心数 |No|
| **BootDiskType** | string | 磁盘类型 |No|
| **DataDiskSize** | int | 数据磁盘大小 |No|
| **DataDiskType** | string | 磁盘类型 |No|
| **Tag** | string | 业务组 |No|
| **ChargeType** | string | 计费模式 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeGroupId** | string | 节点池ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUK8SNodeGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=erWPRmTL
&NodeGroupName=sDJQamTw
&ImageId=SErYualz
&MachineType=ulkHtgvq
&MinimalCpuPlatform=llOxqZiy
&CPU=2
&Mem=9
&GpuType=VHPlqtNm
&GPU=7
&BootDiskType=KLbRaYoT
&DataDiskSize=vNWywYIK
&DataDiskType=zdhEnXgA
&Tag=gsZPoUZG
&ChargeType=yhQCTlsM
&ClusterId=tzEjlYyc
&OrgId=8
&TopOrgId=2
&AzGroupId=6
```

### 响应示例
    
```json
{
  "Action": "AddUK8SNodeGroupResponse",
  "Message": "DMJPRigX",
  "NodeGroupId": "jXKZQgSU",
  "RetCode": 0
}
```





