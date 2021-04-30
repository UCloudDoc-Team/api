# 获取UK8S集群节点信息 - ListUK8SClusterNodeV2

## 简介

获取UK8S集群节点信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUK8SClusterNodeV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | UK8S集群ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeSet** | array[[*NodeInfoV2*](#NodeInfoV2)] | 节点详细信息，见NodeInfoV2。 |**Yes**|
| **TotalCount** | int | 满足条件的节点数量，包括Master。 |**Yes**|

#### 数据模型


#### NodeInfoV2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | Node所在可用区 |**Yes**|
| **NodeId** | string | NodeId，Node在UK8S处的唯一标示，如uk8s-reewqe5-sdasadsda |**Yes**|
| **NodeRole** | string | node角色，枚举值为master、node |**Yes**|
| **NodeStatus** | string | Node的状态 |**Yes**|
| **InstanceType** | string | Node节点的资源类型，枚举值为UHost或UPHost。 |**Yes**|
| **InstanceName** | string | 资源名称，初始值等于NodeId，用户可在UHost或UPHost处修改。 |**Yes**|
| **InstanceId** | string | 资源ID，如uhost-xxxx，或uphost-xxxxx。 |**Yes**|
| **MachineType** | string | 机型类别，分别对应Uhost的MachineType或PHost的PHostType。 |**Yes**|
| **OsType** | string | Node节点的操作系统类别，如Linux或Windows。 |**Yes**|
| **OsName** | string | Node节点的镜像名称。 |**Yes**|
| **CPU** | int | Node节点CPU核数，单位: 个。 |**Yes**|
| **Memory** | int | 内存大小，单位: MB。 |**Yes**|
| **IPSet** | array[[*UHostIPSet*](#UHostIPSet)] | 节点IP信息，详细信息见 UHostIPSet。 |**Yes**|
| **CreateTime** | int | 节点创建时间 |**Yes**|
| **ExpireTime** | int | 节点计费到期时间 |**Yes**|
| **AsgId** | string | 节点所属伸缩组ID，非伸缩组创建出来的节点，伸缩组ID为Default。 |**Yes**|
| **Unschedulable** | boolean | 是否允许Pod调度到该节点，枚举值为true或false。 |**Yes**|
| **KubeProxy** | [*KubeProxy*](#KubeProxy) | kubeproxy信息，详细信息见KubeProxy。 |**Yes**|
| **NodeLogInfo** | string | 加节点时判断是否没有资源，如果返回NORESOURCE则代表没有资源了 |**Yes**|
| **GPU** | int | 节点的GPU颗数。 |No|

#### UHostIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 国际: Internation，BGP: Bgp，内网: Private |No|
| **IPId** | string | IP资源ID (内网IP无对应的资源ID) |No|
| **IP** | string | IP地址 |No|
| **Bandwidth** | int | IP对应的带宽, 单位: Mb (内网IP不显示带宽信息) |No|
| **VPCId** | string | IP地址对应的VPC ID |No|
| **SubnetId** | string | IP地址对应的子网 ID |No|
| **Mac** | string | Mac地址 |No|

#### KubeProxy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Mode** | string | KubeProxy模式，枚举值为[ipvs,iptables] |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUK8SClusterNodeV2
&Region=cn-zj
&ProjectId=tcpNeveH
&ClusterId=UZFeTeQg
```

### 响应示例
    
```json
{
  "Action": "ListUK8SClusterNodeV2Response",
  "MasterList": [
    {
      "AsgId": "ZSoMzQUG",
      "BasicImageName": "AvDDPeuv",
      "CPU": 9,
      "CreateTime": 1,
      "ExpireTime": 9,
      "GPU": 3,
      "HostType": "CiqztSMG",
      "IPSet": [
        {
          "Bandwidth": 1,
          "Default": "fkBpzlPQ",
          "IP": "AEMpLpMr",
          "IPId": "ZJQDIEzr",
          "Mac": "rjizzEse",
          "SubnetId": "bxYSrMgl",
          "Type": "shzOBwxT",
          "VPCId": "bjpJSrMz"
        }
      ],
      "InstanceId": "rbTPwvaj",
      "InstanceName": "zbUQMbej",
      "MachineType": "opgyDvSn",
      "Memory": 9,
      "NodeId": "gNvfqKWV",
      "OsName": "bgpWkLID",
      "OsType": "vkzHZoYO",
      "State": "EyECtWVo",
      "UHostDiskSet": [
        {
          "BackupType": "GPAKbeiX",
          "DiskId": "ILwnaPJR",
          "DiskType": "qIGGJZOD",
          "Drive": "uHjecSxj",
          "Encrypted": "CmdZIplB",
          "IOPS": 4,
          "IsBoot": "svkrxtpA",
          "Name": "QfPxfuar",
          "Size": 3,
          "Type": "WhHaGvPu"
        }
      ],
      "Zone": "flRgPYsL"
    }
  ],
  "NodeList": {},
  "RetCode": 0
}
```





