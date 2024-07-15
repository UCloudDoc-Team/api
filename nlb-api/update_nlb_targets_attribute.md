# 更新后端服务节点属性 - UpdateNLBTargetsAttribute

## 简介

更新后端服务节点属性






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateNLBTargetsAttribute)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateNLBTargetsAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NLBId** | string | 负载均衡实例的ID	 |**Yes**|
| **ListenerId** | string | 监听器的ID |**Yes**|
| **Targets.N.Id** | string | 服务节点的ID |No|
| **Targets.N.Enabled** | boolean | 是否禁用服务节点 |No|
| **Targets.N.Weight** | int | 服务节点的权重。限定取值：[1-100]，默认值1；仅在加权轮询、加权最小连接数算法时有效 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateNLBTargetsAttribute
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=jFiTFBal
&NLBId=iBIfSnrf
&ListenerId=kpMGSJZJ
&Targets=thRDmAWV
&Targets.n.Enabled=true
&Targets.n.Weight=7
```

### 响应示例
    
```json
{
  "Action": "UpdateNLBTargetsAttributeResponse",
  "RetCode": 0
}
```





