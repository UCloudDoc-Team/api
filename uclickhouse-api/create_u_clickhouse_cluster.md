# 创建UClickhouse集群 - CreateUClickhouseCluster

## 简介

创建UClickhouse集群






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUClickhouseCluster)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUClickhouseCluster`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClickhouseMachineTypeId** | string | 集群机型，可通过GetUClickhouseClusterCreateOption接口获取具体值 |**Yes**|
| **DataDiskType** | string | 数据盘类型，可通过GetUClickhouseClusterCreateOption接口获取具体值 |**Yes**|
| **ClickhouseVersion** | string | Clickhouse版本，可通过GetUClickhouseClusterCreateOption接口获取具体版本 |**Yes**|
| **VPCId** | string | VPCID |**Yes**|
| **SubnetId** | string | 子网ID |**Yes**|
| **AdminPassword** | string | 集群管理员密码（需 base64 编码后传入），编码前的密码规则：<br />1.密码长度限8-32个字符<br />2.不能包含[A-Z],[a-z],[0-9]和[@#%^*+=_;:,?!&()-]之外的字符<br />3.需要同时包含两项或以上（大写字母/小写字母/数字/特殊符号） |**Yes**|
| **ShardCount** | int | 分片数量，若传递，则至少1个分片,默认值为1 |No|
| **ReplicateCount** | int | 副本数量，取值为1或2，1为单副本（非高可用），2为双副本（高可用），默认值为高可用（即为2） |No|
| **DataDiskSize** | int | 数据盘大小，最小100，步长为50，默认值为100，单位GB |No|
| **ChargeType** | string | 付费类型，枚举值：Year（年付），Month（月付），Dynamic（时付），默认值为Month,月付 |No|
| **Quantity** | int | 购买时长，默认值为1。月付时，此参数传0，代表购买至月末 |No|
| **BackupId** | string | 备份任务ID，从备份恢复时，该字段必传，此值为备份任务ID，可以从原集群备份任务列表（ListUClickhouseBackups）获取 |No|
| **ClusterName** | string | 实例名称<br />名称规则：<br />1.长度为1-50位的字符<br />2.不能包含_,中文,[A-Z],[a-z],[0-9]之外的非法字符，集群名称默认为clickhouse |No|
| **IsZookeeperHA** | boolean | 是否Zookeeper高可用，true为zookeeper高可用，false为非高可用，默认为true，高可用 |No|
| **IsSecGroup** | string | 是否开启安全组，true为开启，false为不开启，默认为false，不开启安全组 |No|
| **IsMultiZone** | string | 是否多可用区，默认为false |No|
| **ZookeeperMachineTypeId** | string | Zookeeper机型ID，IsZookeeperHA为true时，必传，可通过GetUClickhouseClusterCreateOption接口获取具体值 |No|
| **ZookeeperDataDiskType** | string | Zookeeper数据盘类型，IsZookeeperHA为true时，必传，可通过GetUClickhouseClusterCreateOption接口获取具体值 |No|
| **ZookeeperDataDiskSize** | string | Zookeeper数据盘大小，IsZookeeperHA为true时，必传，最小100，步长为50 |No|
| **SecGroupIds** | string | 安全组ID，IsSecGroup为true时，必传 |No|
| **MultiZones.N** | string | 【数组】可用区名称，IsMultiZone为true时，必传，可通过ListUClickhouseAvailableZone获取支持的可用区 |No|
| **Labels.N.Key** | string | 标签的key |No|
| **Labels.N.Value** | string | 标签的value |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*CreateUClickhouseClusterResponseData*](#CreateUClickhouseClusterResponseData) | 返回数据 |**Yes**|

#### 数据模型


#### CreateUClickhouseClusterResponseData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClusterId** | string | 集群ID |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUClickhouseCluster
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=XrdfPMLL
&InstanceName=mjxEcnFR
&ClickhouseMachineTypeId=UhHMluUU
&ShardCount=6
&ReplicateCount=1
&DataDiskType=aQVAltCJ
&DataDiskSize=6
&ChargeType=wHuvNHEh
&Quantity=3
&ClickhouseVersion=EhfhZaQD
&VPCId=QQYGLIxI
&SubnetId=AvvuFcXx
&AdminUsername=zIIqFHNE
&AdminPassword=YZGaoSmX
&BackupId=EDUBlCcg
&IsZookeeperHA=false
&ZookeeperMachineTypeId=ZEntCScI
&ZookeeperDataDiskType=zFDWBlMt
&ZookeeperDataDiskSize=XYUEQuzN
&IsSecGroup=IKGkESLn
&SecGroupIds=TlFwRvMN
&IsMultiZone=ENDHUvGn
&MultiZones=egcYClwu
&Labels=QpVSUzQT
&IsZookeeperHA=false
&ZookeeperMachineTypeId=RYTiyqKQ
&ZookeeperDataDiskType=UNlYoKQt
&ZookeeperDataDiskSize=XTaKcQgB
&IsSecGroup=SyeaYohT
&SecGroupIds=uargiKNQ
&IsMultiZone=NDONgIPD
&MultiZones.N=Bnfqqarq
&Labels.N=TDAlpbTk
&IsZookeeperHA=true
&ZookeeperMachineTypeId=prqBHEnU
&ZookeeperDataDiskType=smItxbWC
&ZookeeperDataDiskSize=jkyGzaIW
&IsSecGroup=MOGjkvmH
&SecGroupIds=bUkddJTt
&IsMultiZone=rfrfTQEk
&MultiZones.N=LdRwnxsw
&Labels.N=XVhtGlPA
&IsZookeeperHA=true
&ZookeeperMachineTypeId=cZjBLdbA
&ZookeeperDataDiskType=mQTFtdfK
&ZookeeperDataDiskSize=ArHlKzwt
&IsSecGroup=VySFlwqL
&SecGroupIds=rujOPaYw
&IsMultiZone=mZRHnKrn
&MultiZones.N=NRnbwVOT
&Labels.N.Key=iJjyZfCl
&Labels.N.Value=upWBzDtQ
&CouponId=TOCuDgzm
```

### 响应示例
    
```json
{
  "Action": "CreateUClickhouseClusterResponse",
  "Data": {},
  "Message": "dgxphAid",
  "RetCode": 0
}
```





