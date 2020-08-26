# 升降级分布式数据库数据节点的配置 - UpgradeUDDBDataNode

## 简介

升降级分布式数据库数据节点的配置, 提高/降低数据节点的数据容量和内存<br /><br />所有数据节点以及其所挂载的只读实例的配置都受到影响<br /><br />升降级数据节点的配置之后之后, 会按照数据节点新的磁盘和内存大小重新计费<br /><br />如下状态的数据节点实例可以进行这个操作:<br /><br />Shutoff: 已关闭<br />当请求返回成功之后，UDDB实例的状态变成"UpgradingDataNode"，相关数据节点的状态变成"Upgrading"; 如果返回失败, UDDB实例状态保持不变 当UDDB实例升级结束之后, UDDB实例的状态变成"Shutoff"






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpgradeUDDBDataNode)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpgradeUDDBDataNode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UDDBId** | string | UDDB实例ID |**Yes**|
| **DataNodeMemory** | int | 新的数据节点的内存配置, 单位：MB 具体数值参考UDB的内存取值 |**Yes**|
| **DataNodeDiskSpace** | int | 新的数据节点的磁盘大小配置. 单位: GB 具体数值参考UDB的磁盘大小取值. |**Yes**|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpgradeUDDBDataNode
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=zuLSTdbI
&DataNodeMemory=8
&DataNodeDiskSpace=2
&CouponId=BIYpPZeJ
&ProjectId=JnaIDNoQ
```

### 响应示例
    
```json
{
  "Action": "UpgradeUDDBDataNodeResponse",
  "Message": "ZkwoeTyN",
  "RetCode": 0
}
```





