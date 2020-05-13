# 查询清洗服务 - DescribeCleanService

## 简介

查询清洗服务





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeCleanService)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCleanService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id，为空代表查询用户下所有清洗资源；不为空时代表查询指定资源ID的清洗服务；默认为空 |No|
| **CleanRegion** | string | 清洗机房，不传时代表all。查询所有 |No|
| **Offset** | int | 数据偏移量, 默认为0。供分页显示使用 |No|
| **Limit** | int | 返回清洗的最多条目数, 默认为10。供分页显示使用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 符合条件的条目总数 |**Yes**|
| **CleanServiceList** | array[[*CleanServiceList*](#CleanServiceList)] | 清洗服务列表 |**Yes**|

#### 数据模型


#### CleanServiceList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |**Yes**|
| **CreateTime** | string | 创建时间 （时间戳） |**Yes**|
| **ExpiredTime** | string | 过期时间（时间戳） |**Yes**|
| **CleanRegion** | string | 地域 |**Yes**|
| **MaxCleanCapacity** | int | 流量清洗上限防护流量（单位G），5、10、15、20、25 |**Yes**|
| **DefenceStatus** | string | 状态，清洗服务的当前状态<br />当前状态 (清洗中：Cleaning  过期：Expired) |**Yes**|
| **StatusRemarks** | string | 状态的补充说明（正常：Normal 超限：Exceed） |**Yes**|
| **ChargeType** | string | 计费方式（Month:按月，Year:按年） |**Yes**|
| **AutoRenewal** | int | 自动续费<br />1：开启<br />0：关闭 |**Yes**|
| **DefenseIP** | int | 最近一次受攻击的IP |**Yes**|
| **DefenseTime** | string | 最近攻击时间，时间戳 |**Yes**|
| **DefensePeak** | float | 最近攻击流量峰值 |**Yes**|
| **BlockIpNum** | int | 正在被封堵的IP数量 |**Yes**|
| **CleanIpNum** | int | 正在被清洗的IP数量 |**Yes**|
| **BuyMaxCleanCapacityLimit** | int | 允许购买的最大清洗阈值 |**Yes**|
| **PublicTest** | int | 公测标识 |**Yes**|
| **CustomCleanPolicy** | int | 支持自定义清洗阈值配置 |**Yes**|
| **Tips** | string | 提示信息，跟页面前端展示匹配 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCleanService
&Offset=9
&Limit=7
&CleanRegion=RYaHCbJg
```

### 响应示例
    
```json
{
  "Action": "DescribeCleanServiceResponse",
  "CleanServiceList": [
    {
      "AutoRenewal": 1,
      "BlockIpNum": 1,
      "BuyMaxCleanCapacityLimit": 10,
      "ChargeType": "Month",
      "CleanIpNum": 1,
      "CleanRegion": "上海",
      "CreateTime": 1526438569,
      "DefenceStatus": "Started",
      "DefenseFlow": 80.344,
      "DefenseIP": "192.168.254.10",
      "DefenseTime": 1523334896,
      "ExpiredTime": 1529116968,
      "MaxCleanCapacity": 15,
      "ResourceId": "usecure_UCLEAN-dch4di"
    },
    {
      "AutoRenewal": 1,
      "BlockIpNum": 1,
      "BuyMaxCleanCapacityLimit": 10,
      "ChargeType": "Month",
      "CleanIpNum": 1,
      "CleanRegion": "北京",
      "CreateTime": 1526437820,
      "DefenceStatus": "Started",
      "DefenseFlow": 80.344,
      "DefenseIP": "192.168.254.10",
      "DefenseTime": 1523334896,
      "ExpiredTime": 1529116220,
      "MaxCleanCapacity": 5,
      "ResourceId": "usecure_UCLEAN-sei2sx"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





