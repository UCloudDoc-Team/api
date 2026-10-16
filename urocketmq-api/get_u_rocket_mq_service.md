# 获取实例详情 - GetURocketMQService

## 简介

获取指定id的Service的详情









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetURocketMQService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ServiceId** | string | 服务ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ServiceList** | array[[*ServiceDetail*](#ServiceDetail)] | Service 列表, 包含获取的 Service 详情 |**Yes**|

#### 数据模型


#### ServiceDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ChargeType** | string | 付费类型 参考link |**Yes**|
| **ServiceId** | string | Service ID |**Yes**|
| **Name** | string | 名称 |**Yes**|
| **Remark** | string | 描述 |**Yes**|
| **State** | string | 服务状态: Unknown:未知, Available: 可用, Initializing, Deleting:删除中,CreateFailed:创建失败 |**Yes**|
| **SubnetId** | string | subnet id |**Yes**|
| **ExpireTime** | int | 资源有效期 unix timestamp, 单位秒, 对应 PurchaseValue |**Yes**|
| **AutoRenew** | string | 自动续费 1 自动续费，0 不自动续费 |**Yes**|
| **Storage** | int | 存储空间, 单位 GB |**Yes**|
| **TopicLimit** | int | Topic 限额 |**Yes**|
| **Quantity** | int | 购买时长 |**Yes**|
| **VpcId** | string | vpc id |No|
| **Tps** | int | 规格, 具体枚举值待定 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetURocketMQService
&Region=cn-zj
&ProjectId=YOesiTGQ
&ServiceId=uptNNggM
```

### 响应示例
    
```json
{
  "Action": "GetURocketMQServiceResponse",
  "Message": "GMvPZNMW",
  "RetCode": 0,
  "ServiceList": [
    {
      "AutoRenew": 2,
      "ChargeType": 2,
      "ExpireTime": 8,
      "Name": "GRmqkdLR",
      "OrderTime": 6,
      "Region": "cn-zj",
      "Remark": "sgfvJPxX",
      "ServiceId": "SaSKkdku",
      "State": "BwugeEiA",
      "Storage": 4,
      "SubnetId": "unORiqlR",
      "TPS": 4,
      "TopicCount": 4,
      "VPCId": "TGWNXarO"
    }
  ]
}
```





