# 列出UK8S节点池 - ListUK8SNodeGroup

## 简介

列出UK8S节点池









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUK8SNodeGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeGroupList** | array[[*NodeGroupSet*](#NodeGroupSet)] | 节点池列表 |No|

#### 数据模型


#### NodeGroupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **NodeGroupId** | string | 节点池ID |No|
| **NodeGroupName** | string | 节点池名字 |No|
| **ImageId** | string | 镜像ID |No|
| **MachineType** | string | 机型 |No|
| **MinimalCpuPlatform** | string | cpu平台 |No|
| **CPU** | int | 虚拟CPU核数 |No|
| **Mem** | int | 内存大小 |No|
| **GpuType** | string | GPU类型 |No|
| **GPU** | int | GPU卡核心数 |No|
| **BootDiskType** | string | 系统盘类型 |No|
| **BootDiskSize** | int | 系统盘大小 |No|
| **DataDiskSize** | int | 数据盘大小 |No|
| **DataDiskType** | string | 数据盘类型 |No|
| **Tag** | string | 业务组 |No|
| **ChargeType** | string | 付费方式 |No|
| **NodeList** | array[string] | 节点id列表 |No|
| **SubnetId** | string | 子网 ID。默认为集群创建时填写的子网ID，也可以填写集群同VPC内的子网ID。 |No|
| **IsolationGroupId** | string | 硬件隔离组id。可通过DescribeIsolationGroup获取。 |No|
| **MaxPods** | string | int<br />默认110，生产环境建议小于等于110。 |No|
| **UserData** | string | 用户自定义数据。当镜像支持Cloud-init Feature时可填写此字段。注意：1、总数据量大小不超过 16K；2、使用base64编码。 |No|
| **InitScript** | string | 用户自定义Shell脚本。与UserData的区别在于InitScript在节点初始化完毕后才执行，UserData则是云主机初始化时执行。 |No|
| **Taints** | string | Node节点污点，形式为key=value:effect，多组taints用”,“隔开,最多支持五组。 |No|
| **Labels** | string | Node节点标签。key=value形式,多组用”,“隔开，最多5组。 如env=pro,type=game |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUK8SNodeGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=wVpiDplE
&ClusterId=RXIkKKuX
&TopOrgId=8
&OrgId=4
&AzGroup=5
```

### 响应示例
    
```json
{
  "Action": "ListUK8SNodeGroupResponse",
  "NodeGroupList": [
    {
      "BootDiskType": "ceGeUMIV",
      "CPU": 6,
      "ChargeType": "addNhDvH",
      "DataDiskSize": 8,
      "DataDiskType": "qqncHfyc",
      "GPU": 7,
      "GpuType": "neHNFfsx",
      "ImageId": "PVoCRmtW",
      "MachineType": "GJXNpRmz",
      "Mem": 7,
      "MinimalCpuPlatform": "uEqOcnpP",
      "NodeGroupId": "ayLygrGZ",
      "NodeGroupName": "svwqEVOH",
      "NodeList": "ndxnQQhO",
      "Tag": "XUcqKwjh"
    }
  ],
  "RetCode": 0
}
```





