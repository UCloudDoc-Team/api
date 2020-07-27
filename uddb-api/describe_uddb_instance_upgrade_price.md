# 升级UDDB时，获取升级后的价格 - DescribeUDDBInstanceUpgradePrice

## 简介

升级UDDB时，获取升级后的价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDDBInstanceUpgradePrice)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDDBInstanceUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UDDBId** | string | UDDB实例ID |**Yes**|
| **RouterVersion** | string | UDDB路由节点的版本。分为三种： <br />Trival(免费版)： 2中间件节点； QPS：1.5W<br />FeelFree(标准版)： 固定为4中间件节点，后续将根据业务请求量自动扩展，最多扩展到12个节点，QPS为3w - 10w；<br />EnjoyAlone(物理机版)：专享物理机，节点数让客户可选 |**Yes**|
| **RouterNodeNum** | int | 其他版本：该参数可不填；专享版：物理机节点的个数。一台物理机有2个节点 |**Yes**|
| **DataNodeCount** | int | 新的数据节点个数 取值必须>0. |No|
| **DataNodeMemory** | int | 新的数据节点的内存配置, 单位：MB 具体数值参考UDB的内存取值. |No|
| **DataNodeDiskSpace** | int | 新的数据节点的磁盘大小配置. 单位: GB 具体数值参考UDB的磁盘大小取值. |No|
| **DataNodeSlaveCount** | int | 每个数据节点的只读实例个数, 取值必须>=0. |No|
| **InstanceMode** | string | 存储节点的高可用模式， 分为高可用UDB（HA）和普通UDB（Normal），如果不填， 则默认为HA |No|
| **InstanceType** | string | 存储节点和只读实例的磁盘类型。分为：SSD磁盘（SATA_SSD）或普通磁盘(Normal)。 如果不填，则默认为SATA_SSD |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceInfo** | [*PriceInfo*](#PriceInfo) | 价格明细, 参考PriceInfo对象定义 |No|

#### 数据模型


#### PriceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MiddlewarePrice** | float | 中间件路由节点费用 |No|
| **DataNodePrice** | float | 存储节点费用 |No|
| **DataNodeSlavePrice** | float | 只读实例费用 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDDBInstanceUpgradePrice
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=RNmZhzsX
&RouterNodeVersion=Trival
&RouterNodeNum=2
&DataNodeCount=2
&DataNodeMemory=8
&DataNodeDiskSpace=7
&DataNodeSlaveCount=9
&InstanceMode=nHhQyjwr
&InstanceType=PBXTsHdq
&ProjectId=WZUxpnBL
```

### 响应示例
    
```json
{
  "Action": "DescribeUDDBInstanceUpgradePriceResponse",
  "Message": "NhfvJDKU",
  "PriceInfo": [
    {
      "DataNodePrice": 3.76372,
      "DataNodeSlavePrice": 1.77679,
      "MiddlewarePrice": 4.88913
    },
    {
      "DataNodePrice": 2.24776,
      "DataNodeSlavePrice": 7.28714,
      "MiddlewarePrice": 6.95267
    },
    {
      "DataNodePrice": 1.25864,
      "DataNodeSlavePrice": 7.37894,
      "MiddlewarePrice": 5.64989
    },
    {
      "DataNodePrice": 4.35778,
      "DataNodeSlavePrice": 9.76949,
      "MiddlewarePrice": 2.15365
    },
    {
      "DataNodePrice": 8.12559,
      "DataNodeSlavePrice": 8.91499,
      "MiddlewarePrice": 6.88811
    },
    {
      "DataNodePrice": 6.31617,
      "DataNodeSlavePrice": 6.32137,
      "MiddlewarePrice": 1.87756
    },
    {
      "DataNodePrice": 5.51924,
      "DataNodeSlavePrice": 6.76566,
      "MiddlewarePrice": 6.55247
    },
    {
      "DataNodePrice": 3.61715,
      "DataNodeSlavePrice": 8.19212,
      "MiddlewarePrice": 1.75898
    },
    {
      "DataNodePrice": 5.64282,
      "DataNodeSlavePrice": 7.22914,
      "MiddlewarePrice": 4.19762
    },
    {
      "DataNodePrice": 6.65527,
      "DataNodeSlavePrice": 1.26237,
      "MiddlewarePrice": 4.84727
    }
  ],
  "RetCode": 0
}
```





