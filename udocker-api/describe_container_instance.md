# 获取Container实例 - DescribeContainerInstance

## 简介

获取Container实例





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeContainerInstance)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeContainerInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **NodeId** | string | 容器所属节点ID |No|
| **ClusterId** | string | 容器所属资源池ID |No|
| **ContainerIds.N** | string | 容器ID |No|
| **Offset** | int | 偏移量，默认为0 |No|
| **Limit** | int | 总量限制，默认20，最大值10000 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 总数 |**Yes**|
| **ContainerSet** | array[[*ContainerSet*](#ContainerSet)] | 容器列表 |No|

#### 数据模型


#### ContainerSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ContainerId** | string | 容器ID |No|
| **ClusterId** | string | 集群ID |No|
| **NodeId** | string | 节点ID |No|
| **Name** | string | 容器名 |No|
| **Image** | string | 容器镜像 |No|
| **Zone** | string | 可用区 |No|
| **CPU** | float | CPU个数 |No|
| **Memory** | int | 内存容量，MB |No|
| **Cmd** | string | 容器启动命令 |No|
| **State** | string | 状态 |No|
| **IPSet** | array[[*IPSet*](#IPSet)] | IP |No|
| **CreateTime** | int | Unix时间戳 |No|
| **Volume** | string | 容器内挂载的目录 |No|
| **Enviroment** | array[[*EnviromentSet*](#EnviromentSet)] | 环境变量 |No|

#### IPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | IP类型  国际:International, BGP:Bgp, 内网:Private |No|
| **IPId** | string | IP资源ID  （只在当前IP为外网IP时返回） |No|
| **IP** | string | IP地址 |No|
| **Bandwidth** | int | IP对应的带宽, 单位:Mb （只在当前IP为外网IP时返回） |No|
| **VPCId** | string | VPCId |No|
| **SubnetId** | string | 子网ID |No|

#### EnviromentSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | key:val形式 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeContainerInstance
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&NodeId=dnode-xxx
&ClusterId=cluster-xxx
&Offset=0
&Limit=100
```

### 响应示例
    
```json
{
  "Action": "DescribeContainerInstanceResponse",
  "ContainerSet": [
    {
      "CPU": 0,
      "ClusterId": "cluster-xxx",
      "ClusterName": "cluster2",
      "Cmd": "",
      "ComputerDetails": {
        "all_cpus": 4,
        "all_mem": 8192,
        "res_id": "dnode-xxx",
        "subnet_id": "subnet-xxx",
        "vpc_id": "uvnet-xxx"
      },
      "ContainerId": "docker-xxx",
      "ContainerType": "pod",
      "CreateTime": 1529986046,
      "Enviroment": [
        {
          "TZ": "Asia/Shanghai"
        }
      ],
      "IPSet": [
        {
          "IP": "10.10.xxx.xxx",
          "Type": "Private"
        }
      ],
      "Image": "uhub.service.ucloud.cn/ucloud/centos6-ssh:latest",
      "Memory": 0,
      "Name": "service22-pod",
      "NodeId": "dnode-xxx",
      "Parameters": {
        "log-opt": [
          "max-file=2",
          "max-size=10M"
        ]
      },
      "PortMap": "",
      "RegionId": 1000001,
      "State": "RUNNING",
      "SvcName": "service22",
      "TaskId": "docker-xxx",
      "Volume": "",
      "Weight": 100,
      "Zone": "cn-bj2-02"
    },
    {
      "CPU": 0,
      "ClusterId": "cluster-xxx",
      "ClusterName": "cluster2",
      "Cmd": "",
      "ComputerDetails": {
        "all_cpus": 4,
        "all_mem": 8192,
        "res_id": "dnode-xxx",
        "subnet_id": "subnet-xxx",
        "vpc_id": "uvnet-xxx"
      },
      "ContainerId": "docker-xxx",
      "ContainerType": "container",
      "CreateTime": 1529985617,
      "Enviroment": [
        {
          "TZ": "Asia/Shanghai"
        }
      ],
      "IPSet": [
        {
          "IP": "10.10.xxx.xxx",
          "Type": "Private"
        }
      ],
      "Image": "uhub.service.ucloud.cn/ucloud/centos6-ssh:latest",
      "Memory": 0,
      "Name": "Container",
      "NodeId": "dnode-xxx",
      "Parameters": {
        "log-opt": [
          "max-file=2",
          "max-size=10M"
        ]
      },
      "PortMap": "",
      "RegionId": 1000001,
      "State": "RUNNING",
      "SvcName": "",
      "TaskId": "docker-xxx",
      "Volume": ":/data",
      "Weight": 0,
      "Zone": "cn-bj2-02"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





