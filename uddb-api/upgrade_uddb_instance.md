# 升降级分布式数据库中间件的配置 - UpgradeUDDBInstance

## 简介

升降级分布式数据库中间件的配置, 提高/降低请求处理的并发性<br /><br />修改请求处理节点个数之后, 按照所有请求处理节点的总内存容量和CPU核数重新计费<br /><br />如下状态的UDDB实例可以进行这个操作:<br /><br />Running: 系统正常运行中<br />当请求返回成功之后，UDDB实例的状态变成"UpgradingUDDB"; 如果返回失败, UDDB实例状态保持不变 当UDDB实例升级成功之后, UDDB实例的状态变成"Running"; 如果更改过程中出现异常, 状态变成"Abnormal", 或者"Error"






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpgradeUDDBInstance)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpgradeUDDBInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UDDBId** | string | UDDB实例ID |**Yes**|
| **RouterVersion** | string | UDDB路由节点的版本。分为三种： Trival(免费版)： 2中间件节点； QPS：1.5W FellFree(标准版)： 固定为4中间件节点，后续将根据业务请求量自动扩展，最多扩展到12个节点，QPS为3w - 10w； EnjoyAlone(物理机版)：专享物理机，节点数让客户可选 |**Yes**|
| **RouterNodeNum** | int | 其他版本：该参数可不填；专享版：物理机台数 |**Yes**|
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
https://api.ucloud.cn/?Action=UpgradeUDDBInstance
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=pSyBgGsz
&NewRouterVersion=Trival
&NewRouterNodeNum=2
&CouponId=RvAhidRT
&ProjectId=Xpugikyb
```

### 响应示例
    
```json
{
  "Action": "UpgradeUDDBInstanceResponse",
  "Message": "iUhGtWka",
  "RetCode": 0
}
```





