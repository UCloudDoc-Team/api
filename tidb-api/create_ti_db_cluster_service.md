# 创建预付费实例 - CreateTiDBClusterService

## 简介

创建预付费实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateTiDBClusterService)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateTiDBClusterService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 集群名称 |**Yes**|
| **Password** | string | 集群密码 |**Yes**|
| **VPCId** | string | VPC id |**Yes**|
| **SubnetId** | string | 子网ID |**Yes**|
| **PubUlbId** | string | 公网Ulb ID |**Yes**|
| **DTType** | string | 容灾类型：10:同可用区，20:跨可用区，默认是同可用区 |**Yes**|
| **NodeConfig.N.ServerType** | string | 节点类型 |**Yes**|
| **NodeConfig.N.NodeCount** | int | 节点数量 |**Yes**|
| **NodeConfig.N.ConfigId** | string | 节点规格ID |**Yes**|
| **NodeConfig.N.DiskSize** | int | 节点磁盘容量 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： Year，按年付费； Month，按月付费； Dynamic，按小时付费（需开启权限）。默认为月付 |**Yes**|
| **OrderDetail.N.ProductName** | string | 计费项名称，CPU / MEM / DISK |**Yes**|
| **OrderDetail.N.Multiple** | int | 计费项数量 |**Yes**|
| **Coupon** | string | 代金券Id |**Yes**|
| **Quantity** | float | 购买时长。默认: 1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传0，代表了购买至月末 |**Yes**|
| **Ip** | string | 指定Ip地址 |No|
| **Port** | string | 指定端口 |No|
| **PromotionId** | string | 活动ID。若有产品折扣，则由各产品与计费约定。 |No|
| **ActivityId** | int | 活动ID。 |No|
| **RuleId** | int | 活动规则ID。 |No|
| **DbVersion** | string | 集群版本号 |No|
| **TemplateId** | string | 参数模版ID |No|
| **AlertStrategyIds.N** | int | 告警策略IDs |No|
| **SecGroupInfo.N.SecGroupId** | string | 安全组 ID。至多可以同时绑定5个安全组。 |No|
| **SecGroupInfo.N.Priority** | int | 安全组优先级。取值范围[1, 5] |No|
| **Labels.N.Key** | string | 用户资源标签的键值 |No|
| **Labels.N.Value** | string | 用户资源标签的值 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*ServiceData*](#ServiceData) | 详情详情 |**Yes**|

#### 数据模型


#### ServiceData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 服务ID |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateTiDBClusterService
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=blOBPWJc
&Name=iMTHMnMQ
&Password=FtKCWbcW
&VPCId=ORjeezXY
&SubnetId=itMUGQNY
&PubUlbId=WeQAXmPc
&DTType=fiNkIlva
&NewCollationEnabled=9
&NewCollationsEnabledONFirstBootstrap=9
&NodeConfig.ServerType.n=kAodJBnS
&NodeConfig.NodeCount.n=9
&NodeConfig.ConfigId.n=cmIjTfGr
&NodeConfig.DiskSize.n=6
&Ip=irbCUrkH
&Port=xzYEHHGj
&ChargeType=IGGkitjS
&OrderDetail.ProductName.n=lUGoWbBg
&OrderDetail.Multiple.n=3
&Quantity=6.63376
&PromotionId=ynqYAdHH
&ActivityId=tIMIQYTu
&RuleId=OVQBLzVz
&ChargeType=DOsijKmf
&OrderDetail.ProductName.n=ChNDPbAB
&OrderDetail.Multiple.n=9
&Coupon=XkKELZDP
&Quantity=1.12136
&PromotionId=AZFhhXnf
&ActivityId=zqUkeIgK
&RuleId=zhnmXuPw
&ChargeType=IbZfSGct
&OrderDetail.N.ProductName=llKGbvXV
&OrderDetail.N.Multiple=7
&Coupon=RkCCVkpl
&Quantity=5.41324
&PromotionId=uQqsTXPj
&ActivityId=wXEHTSmz
&RuleId=GkvHkzoZ
&DbVersion=sBFALbQE
&TemplateId=vhPzGPgG
&AlertStrategyIds.N=7
&SecGroupInfo.N.SecGroupId=ttKqHHLC
&SecGroupInfo.N.Priority=3
&Labels.N.Key=kEVsquGB
&Labels.N.Value=DvJHgcby
```

### 响应示例
    
```json
{
  "Action": "CreateTiDBClusterServiceResponse",
  "Data": {},
  "RetCode": 0
}
```





