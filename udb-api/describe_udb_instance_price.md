# 获取云数据库价格 - DescribeUDBInstancePrice

## 简介

获取UDB实例价格信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBInstancePrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBInstancePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **MemoryLimit** | int | 内存限制(MB)，单位为MB.<br />目前支持：1000-96000 |**Yes**|
| **DiskSpace** | int | 磁盘空间(GB),暂时支持20(GB) - 3000(GB), 输入不带单位 |**Yes**|
| **DBTypeId** | string | UDB实例的DB版本字符串 |**Yes**|
| **Count** | int | 购买DB实例数量,最大数量为10台, 默认为1台 |No|
| **ChargeType** | string | Year，按年付费； <br />Month，按月付费 <br />Dynamic，按需付费（需开启权限) <br />Trial，试用（需开启权限）<br />默认为月付 |No|
| **Quantity** | int | DB购买多少个"计费时间单位"，默认值为1。<br />比如：买2个月，Quantity就是2。<br />如果计费单位是“按月”，并且Quantity为0，表示“购买到月底” |No|
| **UseSSD** | string | 是否使用SSD，只能填true或false，默认为false |No|
| **SSDType** | string | SSD类型，可选值为"SATA"、"PCI-E"，如果UseSSD为true ，则必填 |No|
| **InstanceMode** | string | 实例的部署类型。可选值为：<br />Normal: 普通单点实例，<br />Slave: 从库实例,<br />HA: 高可用部署实例，<br />默认是Normal |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDBInstancePriceSet*](#UDBInstancePriceSet)] | 价格 参照UDBInstancePriceSet |No|

#### 数据模型


#### UDBInstancePriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | Year， Month， Dynamic，Trial |No|
| **Price** | int | 价格，单位为分 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBInstancePrice
&Region=cn-bj2
&Zone=cn-bj2-04
&Count=1   
&ChargeType=Month   
&Quantity=12
&MemoryLimit=600
&DiskSpace=20
&DBTypeId=mysql-5.5
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBInstancePriceResponse",
  "DataSet": [
    {
      "ChargeType": "Month",
      "Price": 1360
    }
  ],
  "RetCode": 0
}
```





