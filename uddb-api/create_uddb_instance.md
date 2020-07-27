# 创建分布式数据库UDDB - CreateUDDBInstance

## 简介

创建创建分布式数据库UDDB实例, 简称UDDB实例。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDDBInstance)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDDBInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **DBTypeId** | string | UDDB的数据库版本，支持版本如下：mysql-5.6 mysql-5.7. 如果不填，则默认为mysql-5.6 |**Yes**|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **AdminPassword** | string | 管理员密码, 密码需要使用base64加密 |**Yes**|
| **RouterVersion** | string | UDDB路由节点的版本。分为三种： Trival(免费版)： 2中间件节点； QPS：1.5W FellFree(标准版)： 固定为4中间件节点，后续将根据业务请求量自动扩展，最多扩展到12个节点，QPS为3w - 10w； EnjoyAlone(物理机版)：专享物理机，节点数让客户可选 |**Yes**|
| **RouterNodeNum** | int | 其他版本：该参数可不填；专享版：物理机台数 |**Yes**|
| **DataNodeCount** | int | 初始的数据节点个数 取值必须>0. |**Yes**|
| **DataNodeMemory** | int | 新的数据节点的内存配置, 单位：MB 具体数值参考UDB的内存取值. |**Yes**|
| **DataNodeDiskSpace** | int | 新的数据节点的磁盘大小配置. 单位: GB 具体数值参考UDB的磁盘大小取值. |**Yes**|
| **InstanceMode** | string | 存储节点的高可用模式， 分为高可用UDB（HA）和普通UDB（Normal），如果不填， 则默认为HA |No|
| **InstanceType** | string | 存储节点和只读实例的磁盘类型。分为：SSD磁盘（SATA_SSD）或普通磁盘(Normal)。 如果不填，则默认为SATA_SSD |No|
| **ChargeType** | string | 付费类型，可选值如下:Year: 按年付费 Month: 按月付费 Dynamic: 按需付费(单位: 小时) Trial: 免费试用  默认值为: Dynamic |No|
| **Quantity** | int | 购买时长，默认值1 |No|
| **AdminUser** | string | 管理员帐户名，默认root |No|
| **Port** | int | 端口号，mysql默认端口为3306 |No|
| **DataNodeSlaveCount** | int | 每个数据节点的只读实例个数, 取值必须>=0. 默认取值为0. |No|
| **VPCId** | string | VPC的ID |No|
| **SubnetId** | string | 子网ID |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UDDBId** | string | UDDB实例ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDDBInstance
&Region=cn-zj
&Zone=cn-zj-01
&DBTypeId=OWxiTIQe
&InstanceMode=qsYtusPJ
&InstanceType=RQGvEKaJ
&ChargeType=YwFBMGKi
&Quantity=1
&CouponId=rfpseCxo
&Name=ShmgUeLY
&AdminUser=CxboMGYg
&AdminPassword=htaaWdMu
&Port=2
&RouterVersion=Trival
&RouterNodeNum=2
&DataNodeCount=8
&DataNodeMemory=7
&DataNodeDiskSpace=3
&DataNodeSlaveCount=1
&ProjectId=rjqsNObC
&VPCId=tHUaCkTW
&SubnetId=vOPHwPQW
```

### 响应示例
    
```json
{
  "Action": "CreateUDDBInstanceResponse",
  "RetCode": 0,
  "UDDBId": "xxx"
}
```





