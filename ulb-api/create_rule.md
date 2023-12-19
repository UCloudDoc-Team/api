# 创建应用型负载均衡的转发规则 - CreateRule

## 简介

给应用型负载均衡监听器创建一条转发规则






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **LoadBalancerId** | string | 负载均衡实例的ID |**Yes**|
| **ListenerId** | string | 监听器的ID |**Yes**|
| **RuleConditions.N.Type** | string | 匹配条件类型。限定枚举值："Host"/"Path" |**Yes**|
| **RuleConditions.N.HostConfig.MatchMode** | string | 匹配方式。限定枚举值："Regular"/"Wildcard"，默认值："Regular" |No|
| **Values.N** | string | 取值。暂时只支持数组长度为1；取值需符合相关匹配方式的条件；域名匹配时必填 |No|
| **Values.N** | string | 取值。暂时只支持数组长度为1；取值需符合相关条件；路径匹配时必填 |No|
| **RuleActions.N.Type** | string | 动作类型。限定枚举值："Forward"；RuleActions暂支持长度为1 |**Yes**|
| **Targets.N.Id** | string | 转发的后端服务节点的标识ID。限定在监听器的服务节点池里；数组长度可以是0；转发服务节点配置的数组长度不为0时，Id必填 |No|
| **Targets.N.Weight** | int | 转发的后端服务节点的权重。仅监听器负载均衡算法是加权轮询是有效 |No|
| **Pass** | boolean | 当转发的服务节点为空时，规则是否忽略。默认值true |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RuleId** | string | 转发规则的ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateRule
&Region=cn-zj
&ProjectId=KkLjsPqn
&LoadBalancerId=TpQFMTyp
&ListenerId=TBLRaFqM
&RuleConditions.n.Type=OwQlzYTk
&RuleActions.n.Type=CdXoaIEM
&RuleConditions.n.HostConfig.MatchMode=PVAsSDML
&RuleConditions.n.HostConfig.Values.n=leqEAWWl
&RuleConditions.n.PathConfig.Values.n=PwuAChmC
&RuleActions.n.ForwardConfig.Targets.n.Id=kJkvikIW
&RuleActions.n.ForwardConfig.Targets.n.Weight=2
&Pass=true
```

### 响应示例
    
```json
{
  "Action": "CreateRuleResponse",
  "RetCode": 0,
  "RuleId": "qZjWGzsa"
}
```





