# 创建实例 - CreateUESInstance

## 简介

创建实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUESInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUESInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **InstanceName** | string | 实例名称 |**Yes**|
| **NodeConf** | string | 节点配置标识, 支持的机型可通过GetUESNodeConf NodeConfList[].NodeConf |**Yes**|
| **VPCId** | string | VPCID标识 |**Yes**|
| **SubnetId** | string | 子网ID标识 |**Yes**|
| **KibanaNodeConf** | string | Kibana节点配置, 支持的机型可通过GetUESNodeConf NodeConfList[].NodeConf |**Yes**|
| **KibanaNodeDiskConf** | string | Kibana节点磁盘类型 |**Yes**|
| **AppVersion** | string | 应用服务版本号，支持的类型通过GetUESAppVersion AppVersionList[].AppVersion |**Yes**|
| **NodeDiskConf** | string | 磁盘类型 |**Yes**|
| **NodeSize** | int | 节点个数，默认数目为3 |No|
| **NodeDiskSize** | int | 节点磁盘大小，默认为100G |No|
| **ServiceUserName** | string | elasticsearch 服务用户名称，默认为elastic；OpenSearch 服务用户名称，固定为admin |No|
| **ServicePasswd** | string | 服务用户密码，默认为changeme.密码长度限8-30个字符，<br />必须同时包含⼤写字⺟，⼩写字⺟和数字。⽆特殊字符。用户密码Base64加密。 |No|
| **AppName** | string | 应用名称，支持的类型通过GetUESAppVersion AppVersionList[].AppName, <br />默认为elasticsearch |No|
| **Remark** | string | 备注，默认为空 |No|
| **ChargeType** | string | 计费类型，默认为Month |No|
| **Quantity** | int | 计费长度，默认为1 |No|
| **MasterConf** | string | 主节点类型标示，支持的机型可通过GetUESNodeConf NodeConfList[].NodeConf, 默认为空 |No|
| **BusinessId** | string | 业务组ID标识 |No|
| **CoordinatingNodeConf** | string | Coordinating节点机型配置，, 支持的机型可通过GetUESNodeConf NodeConfList[].NodeConf,  默认为空 |No|
| **CoordinatingNodeSize** | int | Coordinating节点数量 |No|
| **CoordinatingNodeDiskConf** | string | Coordinating节点磁盘类型 |No|
| **IsSecGroup** | boolean | 是否开启安全组，默认为false |No|
| **SecGroupIds.N** | string | 安全组ID，开启安全组必填，至多可以同时绑定5个安全组 |No|
| **IsMultiZone** | boolean | 是否为多可用区，默认为false |No|
| **MultiZones.N** | string | 多可用区名称，默认空数组 [] |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceId** | string | 实例ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUESInstance
&Region=cn-zj
&Zone=cn-zj-01
&InstanceName=ZeXQVxiP
&ServiceVersion=sgdENTDQ
&CreateType=LomCaSWX
&NodeConf=TPIwHduf
&ClusterSize=6
&ServiceType=BWhUHwNN
&ServiceName=OiCfqTTH
&ServiceUserName=zyOujNDP
&ServicePasswd=KuwVvDMs
&ServicePort=qXuXFuAH
&AppName=iHPFpCTJ
&Remark=yODtVBpO
&VPCId=qMxhRAtC
&SubnetId=BqzYsBTv
&ChargeType=ahlebtPH
&NetworkType=iUKNrXRf
&Quantity=3
&MasterConf=FtaYLYer
&MasterSize=7
&NodeSize=5
&BusinessId=wCjULXTr
&MasterDiskSize=8
&NodeDiskSize=7
&DiskConf=WDjnBpSi
&Secured=true
&KibanaNodeConf=QUdMopQJ
&KibanaNodeSize=5
&KibanaNodeDiskConf=XctXOZsp
&KibanaNodeDiskSize=4
&CoordinatingNodeConf=NUMTBWfx
&CoordinatingNodeSize=2
&CoordinatingNodeDiskConf=sOIFIrFU
&CoordinatingNodeDiskSize=8
&BackendVersion=4
&IsSecGroup=false
&SecGroupIds.N=OQMmqlAu
&IsMultiZone=false
&MultiZones.N=PRtJAfpm
&AppVersion=DQVhpgCu
```

### 响应示例
    
```json
{
  "Action": "CreateUESInstanceResponse",
  "Message": "eTVIGrHX",
  "RetCode": 0,
  "UESInstanceId": "ues-gyyckt"
}
```





