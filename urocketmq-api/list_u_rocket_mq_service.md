# 获取实例列表 - ListURocketMQService

## 简介

获取 Service 列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListURocketMQService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Limit** | int | 最多返回的条目数量, (0, 1000], 默认 20 条 |No|
| **Offset** | int | 查询起始位置, [0, ∞) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ServiceList** | array[[*ServiceBaseInfo*](#ServiceBaseInfo)] | Service 列表, 包含获取的 Service 详情 |**Yes**|

#### 数据模型


#### ServiceBaseInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | Service 所在地域 |**Yes**|
| **Remark** | string | 描述 |**Yes**|
| **ServiceId** | string | Service Id |**Yes**|
| **Name** | string | Service Name |**Yes**|
| **State** | string | 服务状态:。枚举值为：Unknown：未知；Available：可用；Initializing：初始化；Deleting：删除中；CreateFailed：创建失败；Closing：停服中；Closed：已停服；Recovering：停服恢复中；CloseFailed：停服失败；RecoverFailed：停服恢复失败；Upgrading：升级中；UpgradeFailed：升级失败；DeleteFailed：删除失败。 |**Yes**|
| **Address** | string | Service 内网接入地址 |**Yes**|
| **CreateTime** | int | Service 创建时间, Unix timestamp 秒 |**Yes**|
| **Storage** | int | 消息队列存储空间, 单位：GB |**Yes**|
| **VpcId** | string | vpc id |**Yes**|
| **SubnetId** | string | subnet id |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为：Year：按年付费；Month，按月付费；Dynamic，按小时预付费。 |**Yes**|
| **Tps** | int | 实例规格 Tps |**Yes**|
| **TopicLimit** | int | Topic 配额 |**Yes**|
| **IsExpire** | string | 资源是否过期。枚举值为：Yes：已过期；No：未过期 |**Yes**|
| **Mode** | string | 网络模式。枚举值为：Unknown：未知；PrivateNet：内网；PublicNet：外网。 |**Yes**|
| **AddressExtranet** | string | Service 外网接入地址 |**Yes**|
| **ExpireTime** | int | 资源有效期, Unix timestamp 秒 |**Yes**|
| **AutoRenew** | string | 是否自动续费。枚举值为：Yes：是；No：否。 |**Yes**|
| **Tag** | string | 业务组。Default：未分组 |**Yes**|
| **Edition** | string | 版本类别。枚举值为：Unknown：未知；Beta：测试版；Enterprise：企业版。 |**Yes**|
| **FileReservedTime** | int | 消息存储时长，单位：天 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListURocketMQService
&Region=cn-zj
&ProjectId=zIWgThcE
&Limit=4
&Offset=6
```

### 响应示例
    
```json
{
  "Action": "ListURocketMQServiceResponse",
  "Message": "SoXGUyZH",
  "RetCode": 0,
  "ServiceList": [
    {
      "Address": "RlWTCGgV",
      "ChargeType": "Year",
      "CreateTime": 2,
      "Name": "vSvWCFtR",
      "Region": "LawhFXVi",
      "Remark": "QjpXWcCk",
      "ServiceId": "oYvBuuXU",
      "State": "Unknown",
      "Storage": 3,
      "SubnetId": "dSedXjym",
      "TopicCount": 3,
      "VPCId": "qMzPIiMS"
    }
  ]
}
```





