# 获取虚拟机列表 - DescribeUEcVHost

## 简介

获取虚拟机列表 2.0









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUEcVHost`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **IdcId.N** | string | Idc机房id。默认全部机房 |No|
| **NodeId.N** | string | 节点id，创建节点时生成的id。默认全部节点 |No|
| **Offset** | int | 数据偏移量，默认0，非负整数 |No|
| **Limit** | int | 返回数据长度， 默认20，非负整数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的节点总数 |No|
| **NodeList** | array[[*NodeInfo*](#NodeInfo)] | 节点列表 |No|

#### 数据模型


#### NodeInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NodeName** | string | 节点名称 |No|
| **NodeId** | string | 节点ID |No|
| **CoreNum** | int | Cpu核数 |No|
| **MemSize** | int | 节点内存大小，单位GB |No|
| **SysDiskSize** | int | 系统盘大小， 单位GB |No|
| **DiskSize** | int | 数据盘大小， 单位GB |No|
| **State** | int | 节点状态，1部署中，2待启动，3启动中，4运行中，5正在停止，6已停止，7正在更新，8正在重启，9正在删除， 10已经删除,11异常 |No|
| **NetLimit** | int | 节点带宽限制， 单位Mbs |No|
| **IdcId** | string | 机房ID |No|
| **OcName** | string | 机房名称 |No|
| **Province** | string | 省份 |No|
| **City** | string | 城市 |No|
| **Type** | int | 运营商类型： 0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通 |No|
| **ChargeType** | int | 付费类型：1按时, 2按月,3按年 |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpiredTime** | int | 过期时间 |No|
| **ImageName** | string | 镜像名称 |No|
| **NodeIpList** | array[[*NodeIpList*](#NodeIpList)] | 外网ip集合（详情参考NodeIpList） |No|
| **FirewallId** | string | 防火墙Id |No|
| **ProductType** | string | 机器类型(normal-经济型,hf-标准型,g-GPU型) |No|
| **InnerIps** | array[string] | 内网ip列表 |No|

#### NodeIpList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ip** | string | 外网ip |No|
| **Isp** | string | 运营商 |No|
| **IspName** | string | 运营商名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUEcVHost
&ProjectId=mgvpviWs
&IdcId.n=ipckEAYE
&NodeId.n=BWbWInyo
&Offset=5
&Limit=7
```

### 响应示例
    
```json
{
  "Action": "DescribeUEcVHostResponse",
  "NodeList": [
    {
      "ChargeType": 5,
      "City": "IDEBpXJt",
      "CoreNum": 6,
      "CreateTime": 3,
      "DiskSize": 6,
      "ExpiredTime": 6,
      "FirewallId": "IdADaLNf",
      "IdcId": "LmHwaXpN",
      "ImageName": "SgSGAchm",
      "MemSize": 1,
      "NetLimit": 2,
      "NodeId": "VGGLRHtb",
      "NodeIpList": [
        {
          "Ip": "jvWznvrh",
          "Isp": "FEdZNdIg",
          "IspName": "nIKhSjbE"
        }
      ],
      "NodeName": "xUptzCGU",
      "OcName": "eSdJfvFQ",
      "ProductType": "AdQQeKsE",
      "Province": "bhIuwEzj",
      "State": 2,
      "SysDiskSize": 2,
      "Type": 2
    }
  ],
  "RetCode": 0,
  "TotalCount": 3
}
```





