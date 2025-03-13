# 创建实例 - CreateURocketMQService

## 简介

创建一个RocketMQ服务









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateURocketMQService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | Service 名称. 正则检查: ^[a-zA-Z0-9-_]{1,36}$ |**Yes**|
| **Storage** | int | 消息存储空间, 单位 GB, 根据TPS的不同有不同的可选值。20000:[300,2000],50000:[700,2800],100000:[1500,5000],200000:[2000,8000] |**Yes**|
| **VPCId** | string | VPC ID, 默认为当前地域的默认 VPC |**Yes**|
| **SubnetId** | string | 子网 ID, 默认为当前地域的默认子网 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： Year，按年付费； Month，按月付费；Dynamic，按小时预付费 |**Yes**|
| **Tps** | string | 每秒事务处理量。支持20000、50000、100000、200000 |**Yes**|
| **Mode** | string | 实例网络类型，唯一值：PrivateNet |**Yes**|
| **Edition** | string | 版本，唯一值：Enterprise |**Yes**|
| **Quantity** | int | 购买时长。月付时quantity传0代表购买至月末，小时付只支持quantity传0或不传，年付quantity不支持传0 |No|
| **Remark** | string | 备注 |No|
| **Tag** | string | 业务组tag，默认值：Default |No|
| **FileReservedTime** | string | 消息最长保留时长，默认值：3 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ServiceId** | string | 新建 Service 的 ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateURocketMQService
&Region=cn-zj
&ProjectId=edbKnkbr
&Name=zhQpmDFA
&TPS=tZiqcgLK
&TopicLimit=25
&Storage=1
&VPCId=IWYGphNn
&SubnetId=VeERPmRM
&ChargeType=Year
&Quantity=9
&Remark=EdQGxpHS
&Remark=iNqWLhHU
&Mode=PrivateNet：内网模式；PublicNet：外网模式
&Tag=idcfHQMY
&Edition=cJUoTkTu
&FileReservedTime=fhRWEiwS
```

### 响应示例
    
```json
{
  "Action": "CreateURocketMQServiceResponse",
  "Message": "bjtIbiDr",
  "RetCode": 0,
  "ServiceId": "amhugDFb"
}
```





