# 获得容器组信息 - DescribeUEdnHolder

## 简介

获得容器组信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUEdnHolder`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **HolderId.N** | string | 容器组资源id |No|
| **Limit** | int | 返回数据长度，默认为20，非负整数 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0。非负整数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **HolderList** | array[[*HolderList*](#HolderList)] | 容器组列表（详情参考HolderList） |**Yes**|
| **TotalCount** | int | 满足条件的容器组总数 |**Yes**|

#### 数据模型


#### HolderList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 容器组资源id |No|
| **HolderName** | string | 容器组名称 |No|
| **SubnetId** | string | 容器组子网id |No|
| **InnerIp** | string | 容器组内网ip |No|
| **IpList** | array[string] | 容器组外网ip集合 |No|
| **State** | int | 容器组运行状态0：初始化；1：拉取镜像；2：启动中；3：运行中；4：错误；5：正在重启；6：正在删除；7：已经删除；8：容器运行错误；9：启动失败；99：异常<br /> |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpireTime** | int | 过期时间 |No|
| **Type** | int | 线路类型（运营商类型： 0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通） |No|
| **IdcId** | string | 机房id |No|
| **OcName** | string | 机房名称 |No|
| **Province** | string | 省份名称 |No|
| **City** | string | 城市名称 |No|
| **RestartStrategy** | int | 0：总是；1：失败是；2：永不 |No|
| **MachineType** | string | 机器类型（normal-标准型，hf-高性能型） |No|
| **DockerCount** | int | 容器数量 |No|
| **DockerInfo** | array[[*DockerInfo*](#DockerInfo)] | 容器信息（详情参考DockerInfo） |No|
| **ProductType** | string | 机器类型（normal通用型，hf高性能型） |No|
| **NetLimit** | int | 外网绑定的带宽 |No|
| **FirewallId** | string | 外网防火墙id |No|

#### DockerInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CpuCores** | float | CPU核数（/核）精度0.1核 |No|
| **MemSize** | float | 内存大小（Gi） |No|
| **Name** | string | 容器名称 |No|
| **State** | int | 容器状态，0：初始化；1：拉取镜像；2：拉取镜像失败；3：启动中；4：运行中；5：正在停止；<br />6：已停止；7：已删除；8：镜像拉取成功；9：启动失败；99：异常  |No|
| **ImageName** | string | 镜像名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUEdnHolder
&ProjectId=nrtpFKzk
&HolderId.n=wWPbYTIf
&Limit=8
&Offset=9
```

### 响应示例
    
```json
{
  "Action": "DescribeUEdnHolderResponse",
  "HolderList": [
    {
      "City": "nnbPgjPC",
      "CreateTime": 9,
      "DockerCount": 9,
      "DockerInfo": [
        {
          "CpuCores": 6.42338,
          "ImageName": "tqutfzwB",
          "MemSize": 3.36775,
          "Name": "XStddabi",
          "State": 6
        }
      ],
      "ExpireTime": 6,
      "FirewallId": "aVUFxjec",
      "HolderName": "xHaWQPDc",
      "IdcId": "joTJkTVt",
      "InnerIp": "FCvBQACT",
      "IpList": [
        "DhLzUarr"
      ],
      "MachineType": "EOTTpmAn",
      "NetLimit": 2,
      "OcName": "paEQBctD",
      "ProductType": "yFDAaAvl",
      "Province": "yWnzrzZh",
      "ResourceId": "xmjdAbWp",
      "RestartStrategy": 1,
      "State": 3,
      "SubnetId": "GqnEKPaQ",
      "Type": 3
    }
  ],
  "RetCode": 0,
  "TotalCount": 6
}
```





