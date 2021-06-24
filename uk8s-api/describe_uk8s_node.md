# 获取 UK8S 节点详情 - DescribeUK8SNode

## 简介

用于获取 UK8S 节点详情









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUK8SNode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | UK8S 集群 Id |**Yes**|
| **Name** | string | K8S 节点IP或者节点ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Name** | string | 节点名称 |**Yes**|
| **Labels** | array[string] | 字符串数组，每一项是类似 "kubernetes.io/arch=amd64" 的标签 |**Yes**|
| **Annotations** | array[string] | 字符串数组，每一项是类似 "node.alpha.kubernetes.io/ttl=0" 的注解 |**Yes**|
| **CreationTimestamp** | int | 时间戳，单位是 秒 |**Yes**|
| **ProviderID** | string | 字符串，如："UCloud://cn-sh2-02//uk8s-vsc0vgob-n-mpzxc"  |**Yes**|
| **KernelVersion** | string | 内核版本，如："4.19.0-6.el7.ucloud.x86_64" |**Yes**|
| **OSImage** | string | 操作系统类型，如："CentOS Linux 7 (Core)" |**Yes**|
| **ContainerRuntimeVersion** | string | 容器运行时版本，如："docker://18.9.9" |**Yes**|
| **KubeletVersion** | string | kubelet 版本 |**Yes**|
| **KubeProxyVersion** | string | kubeproxy 版本 |**Yes**|
| **InternalIP** | string | 内部 IP 地址 |**Yes**|
| **Hostname** | string | 主机名 |**Yes**|
| **AllocatedPodCount** | int | 已分配到当前节点的 Pod 数量 |**Yes**|
| **PodCapacity** | int | 节点允许的可分配 Pod 最大数量 |**Yes**|
| **Unschedulable** | boolean | 是否禁止调度 |**Yes**|
| **CPUCapacity** | string | 节点 CPU 总量 |**Yes**|
| **MemoryCapacity** | string | 节点内存总量 |**Yes**|
| **MemoryRequests** | string | 节点上已分配 Pod 的内存请求量 |**Yes**|
| **MemoryRequestsFraction** | string | 节点上已分配 Pod 的内存请求量占内存总量的比例，如返回值为 "4.5"，则意味着请求量占总量的 4.5% |**Yes**|
| **MemoryLimits** | string | 节点上已分配 Pod 的内存限制量 |**Yes**|
| **MemoryLimitsFraction** | string | 节点上已分配 Pod 的内存限制量占内存总量的比例，如返回值为 "18"，则意味着限制量占总量的 18% |**Yes**|
| **CPURequests** | string | 节点上已分配 Pod 的 CPU 请求量 |**Yes**|
| **CPURequestsFraction** | string | 节点上已分配 Pod 的 CPU 请求量占 CPU 总量的比例 |**Yes**|
| **CPULimits** | string | 节点上已分配 Pod 的 CPU 限制值 |**Yes**|
| **CPULimitsFraction** | string | 节点上已分配 Pod 的 CPU 限制值占 CPU 总量的比例 |**Yes**|
| **Conditions** | array[[*K8SNodeCondition*](#K8SNodeCondition)] | 节点状态数组 |**Yes**|
| **ContainerImages** | array[string] | 节点上镜像名称数组 |**Yes**|
| **Taints** | array[string] | 字符串数组，每一项是类似 "node-role.kubernetes.io/master:NoSchedule" 的污点 |No|

#### 数据模型


#### K8SNodeCondition

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | Condition 类型，如 MemoryPressure、DiskPressure、PIDPressure、Ready |No|
| **Status** | string | 状态，False、True |No|
| **LastProbeTime** | string | 最后一次上报状态的时间 |No|
| **LastTransitionTime** | string | 最后一次状态转变时间 |No|
| **Reason** | string | 状态变化的原因 |No|
| **Message** | string | 状态变化的描述信息 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUK8SNode
&Region=cn-zj
&ProjectId=sElnRLjI
&ClusterId=totqQYHI
&Name=ErXQmXnS
```

### 响应示例
    
```json
{
  "Action": "DescribeUK8SNodeResponse",
  "AllocatedPodCount": 6,
  "Annotations": [
    "tUWHbrau"
  ],
  "CPUCapacity": "tBszdZRU",
  "CPULimits": "nGbRDmDr",
  "CPULimitsFraction": "LbRKZfsS",
  "CPURequests": "cvVLzNiY",
  "CPURequestsFraction": "wlEcpxok",
  "Conditions": [
    {
      "LastProbeTime": "FWAXrjEN",
      "LastTransitionTime": "KLsUrcTC",
      "Message": "VxQgKfIh",
      "Reason": "UGvztFUN",
      "Status": "CtIFlmpX",
      "Type": "mHcsdTJk"
    }
  ],
  "ContainerImages": [
    "txoXMWDk"
  ],
  "ContainerRuntimeVersion": "zBeQNCmz",
  "CreationTimestamp": 9,
  "Hostname": "HBdXzYsk",
  "InternalIP": "pyyLHaZv",
  "KernelVersion": "gClfaDNr",
  "KubeProxyVersion": "LPRmIqRm",
  "KubeletVersion": "bWvoYPZk",
  "Labels": [
    "lJIBSxcK"
  ],
  "MemoryCapacity": "AObOjZst",
  "MemoryLimits": "TGUARMCd",
  "MemoryLimitsFraction": "LvrhQhjA",
  "MemoryRequests": "RslUIMdZ",
  "MemoryRequestsFraction": "WuedwXMx",
  "Message": "sNFzyWny",
  "Name": "OepprctA",
  "OSImage": "wQyBoQPR",
  "PodCapacity": 9,
  "ProviderID": "NfHgjXUd",
  "RetCode": 0,
  "Taints": [
    "RnidVmEy"
  ],
  "Unschedulable": false
}
```





