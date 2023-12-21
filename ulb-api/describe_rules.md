# 描述应用型负载均衡转发规则 - DescribeRules

## 简介

描述一条指定的转发规则或者一个应用型负载均衡监听器下的所有转发规则

?> 默认规则的Weight与target的真实Weight保持同步




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeRules)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeRules`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **LoadBalancerId** | string | 应用型负载均衡实例的ID |**Yes**|
| **ListenerId** | string | 监听器的ID |**Yes**|
| **RuleId** | string | 应用型负载均衡转发规则的ID。指定RuleId，则只描述该规则 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Rules** | array[[*Rule*](#Rule)] | 转发规则信息 |**Yes**|

#### 数据模型


#### Rule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleId** | string | 转发规则的ID |No|
| **RuleConditions** | array[[*RuleCondition*](#RuleCondition)] | 转发规则匹配条件。具体结构详见 RuleCondition |No|
| **RuleActions** | array[[*RuleAction*](#RuleAction)] | 转发动作。具体规则详见RuleAction |No|
| **IsDefault** | boolean | 是否为默认转发规则 |No|
| **Pass** | boolean | 当转发的服务节点为空时，规则是否忽略 |No|

#### RuleCondition

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 匹配条件类型。限定枚举值：Host，Path |**Yes**|
| **HostConfig** | [*HostConfigSet*](#HostConfigSet) | 域名相关配置。Type为Host时必填。具体结构详见 HostConfigSet |No|
| **PathConfig** | [*PathConfigSet*](#PathConfigSet) | 路径相关配置。Type为Path时必填。具体结构详见 PathConfigSet |No|

#### RuleAction

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 动作类型。限定枚举值：Forward  |**Yes**|
| **ForwardConfig** | [*ForwardConfigSet*](#ForwardConfigSet) | 转发服务节点相关配置。 具体结构详见 ForwardConfigSet  |No|

#### ForwardConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Targets** | array[[*ForwardTargetSet*](#ForwardTargetSet)] | 转发的后端服务节点。限定在监听器的服务节点池里；数组长度可以为0。具体结构详见 ForwardTargetSet |**Yes**|

#### ForwardTargetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 服务节点的标识ID |**Yes**|
| **Weight** | int | 权重。仅监听器负载均衡算法是加权轮询是有效；取值范围[1-100]，默认值为1 |No|

#### HostConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Values** | array[string] | 取值。暂时只支持数组长度为1； 取值需符合相关匹配方式的条件 |**Yes**|
| **MatchMode** | string | 匹配方式。限定枚举值：Regular-正则，Wildcard-泛域名； 默认值：Regular  |No|

#### PathConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Values** | array[string] | 取值。暂时只支持数组长度为1； 取值需符合相关匹配方式的条件 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeRules
&Region=cn-zj
&ProjectId=AONmKvcb
&LoadBalancerId=cCWlIOts
&ListenerId=NmxHLcXL
&RuleId=vNcPniOK
```

### 响应示例
    
```json
{
  "Action": "DescribeRulesResponse",
  "RetCode": 0,
  "Rules": [
    {
      "IsDefault": true,
      "Pass": false,
      "RuleActions": [
        {
          "ForwardConfig": {},
          "Type": "RmzLzQXc"
        }
      ],
      "RuleConditions": [
        {
          "HostConfig": {},
          "PathConfig": {},
          "Type": "cn-zj"
        }
      ],
      "RuleId": "GHOQYSjh"
    }
  ]
}
```





