# 获取分布式数据库UDDB价格 - DescribeUDDBInstancePrice

## 简介

获取分布式数据库UDDB价格





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDDBInstancePrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDDBInstancePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **RouterVersion** | string | UDDB路由节点的版本。分为三种： <br />Trival(免费版)： 2中间件节点； QPS：1.5W<br />FeelFree(标准版)： 固定为4中间件节点，后续将根据业务请求量自动扩展，最多扩展到12个节点，QPS为3w - 10w；<br />EnjoyAlone(物理机版)：专享物理机，节点数让客户可选 |**Yes**|
| **RouterNodeNum** | int | 其他版本：该参数可不填；专享版：物理机节点个数。一台物理机有2个节点 |**Yes**|
| **DataNodeCount** | int | 初始的数据节点个数 取值必须>0. |**Yes**|
| **DataNodeMemory** | string | 新的数据节点的内存配置, 单位：MB 具体数值参考UDB的内存取值. |**Yes**|
| **DataNodeDiskSpace** | int | 新的数据节点的磁盘大小配置. 单位: GB 具体数值参考UDB的磁盘大小取值. |**Yes**|
| **ChargeType** | string | 付费类型，可选值如下: Year: 按年付费 Month: 按月付费 Dynamic: 按需付费(单位: 小时) Trial: 免费试用 默认值为: Dynamic |No|
| **Quantity** | int | 购买时长，默认值1 |No|
| **DataNodeSlaveCount** | int | 每个数据节点的只读实例个数, 取值必须>=0. 默认取值为0. |No|
| **InstanceMode** | string | 存储节点的高可用模式， 分为高可用UDB（HA）和普通UDB（Normal），如果不填， 则默认为HA |No|
| **InstanceType** | string | 存储节点和只读实例的磁盘类型。分为：SSD磁盘（SATA_SSD）或普通磁盘(Normal)。 如果不填，则默认为SATA_SSD |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceInfo** | [*PriceDetailInfo*](#PriceDetailInfo) | 价格明细, 参考PriceDetailInfo对象定义 |No|

#### 数据模型


#### PriceDetailInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MiddlewarePrice** | float | 中间件路由节点费用 |No|
| **DataNodePrice** | float | 存储节点费用 |No|
| **DataNodeSlavePrice** | float | 只读实例费用 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDDBInstancePrice
&Region=cn-zj
&Zone=cn-zj-01
&ChargeType=jqinQilx
&Quantity=7
&RouterVersion=Trival
&RouterNodeNum=2
&DataNodeCount=3
&DataNodeMemory=CVblcUbp
&DataNodeDiskSpace=6
&DataNodeSlaveCount=6
&ProjectId=yEccPuQW
```

### 响应示例
    
```json
{
  "Action": "DescribeUDDBInstancePriceResponse",
  "PriceInfo": {
    "DataNodePrice": 6543.21,
    "DataNodeSlavePrice": 6543.21,
    "MiddlewarePrice": 1234.56
  },
  "RetCode": 0
}
```





