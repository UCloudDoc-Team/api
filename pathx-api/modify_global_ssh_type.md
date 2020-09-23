# 修改GlobalSSH实例类型 - ModifyGlobalSSHType

## 简介

修改GlobalSSH实例类型，仅支持低版本升级到高版本，不支持高版本降级到低版本



!> 免费版可以升级为基础或企业版，收费版不可降级为免费版并且企业版不能降级为基础版（需要先删实例再重建免费版本）


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyGlobalSSHType)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyGlobalSSHType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 实例ID,资源唯一标识 |**Yes**|
| **InstanceType** | string | 取值范围["Enterprise","Basic"]，分别对应企业版和基础版，表示升级后的实例类型。比如从Free版本升级为Basic版或Enterprise版，不可从收费版降级为免费版，或从企业版降级为基础版 |**Yes**|
| **ChargeType** | string | 支付方式，如按月、按年、按时 |No|
| **Quantity** | string | 购买时间，当ChargeType为Month，Quantity为0代表购买到月底 |No|
| **CouponId** | string | 可抵扣费用的券，通常不使用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyGlobalSSHType
&ProjectId=org-xxx
&InstanceId=uga-xxxx
&InstanceType=Basic
&ChargeType=Year
&Quantity=jOnIjCyx
&CouponId=VSOiJRdD
```

### 响应示例
    
```json
{
  "Action": "ModifyGlobalSSHTypeResponse",
  "Message": "SpHGGzwG",
  "RetCode": 0
}
```





