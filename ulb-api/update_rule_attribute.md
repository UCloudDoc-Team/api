# 更新应用型负载均衡的转发规则属性 - UpdateRuleAttribute

## 简介

更新应用型负载均衡监听器的一条转发规则的属性






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateRuleAttribute)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateRuleAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **LoadBalancerId** | string | 负载均衡实例的ID |**Yes**|
| **ListenerId** | string | 监听器的ID |**Yes**|
| **RuleId** | string | 转发规则的ID |**Yes**|
| **RuleConditions.N.Type** | string | 匹配条件类型。限定枚举值："Host"/"Path"；RuleConditions数组长度不为0时必填 |No|
| **RuleConditions.N.HostConfig.MatchMode** | string | 匹配方式。限定枚举值："Regular"/"Wildcard"，默认值："Regular" |No|
| **RuleConditions.N.HostConfig.Values.N** | string | 取值。暂时只支持数组长度为1；取值需符合相关匹配方式的条件；修改域名匹配时必填 |No|
| **RuleConditions.N.PathConfig.Values.N** | string | 取值。暂时只支持数组长度为1；取值需符合相关条件；修改路径匹配时必填 |No|
| **RuleActions.N.Type** | string | 动作类型。限定枚举值："Forward"；RuleActions数组长度不为0时必填 |No|
| **RuleActions.N.ForwardConfig.Targets.N.Id** | string | 转发的后端服务节点的标识ID。限定在监听器的服务节点池里；数组长度可以是0；转发服务节点配置的数组长度不为0时，Id必填 |No|
| **RuleActions.N.ForwardConfig.Targets.N.Weight** | int | 转发的后端服务节点的权重。仅监听器负载均衡算法是加权轮询是有效 |No|
| **RuleActions.N.Order** | int | 转发规则动作执行的顺序，取值为1\~1000，按值从小到大执行动作。值不能为空，不能重复。<br /><br />Forward、FixedResponse 类型的动作不判断 Order，最后一个执行 |No|
| **RuleActions.N.InsertHeaderConfig.Key** | string | 插入的 header 字段名称，长度为 1\~40 个字符，支持大小写字母 a\~z、数字、下划线（_）和短划线（-）。头字段名称不能重复用于InsertHeader中。<br /><br />header 字段不能使用以下(此处判断大小写不敏感)<br /><br />x-real-ip、x-forwarded-for、x-forwarded-proto、x-forwarded-srcport、ucloud-alb-trace、connection、upgrade、content-length、transfer-encoding、keep-alive、te、host、cookie、remoteip、authority |No|
| **RuleActions.N.InsertHeaderConfig.ValueType** | string | 头字段内容类型。取值：<br />UserDefined：用户指定。<br /><br />ReferenceHeader：引用用户请求头中的某一个字段。<br /><br />SystemDefined：系统定义。 |No|
| **RuleActions.N.InsertHeaderConfig.Value** | string | 插入的 header 字段内容。<br /><br />ValueType 取值为 SystemDefined 时取值如下：<br />ClientSrcPort：客户端端口。<br />ClientSrcIp：客户端 IP 地址。<br />Protocol：客户端请求的协议（HTTP 或 HTTPS)。<br />RuleID：客户端请求命中的转发规则ID。<br />ALBID：ALB ID。<br />ALBPort：ALB 端口。<br /><br /><br />ValueType 取值为 UserDefined 时：<br /><br />可以自定义头字段内容，限制长度为 1\~128 个字符，只支持 ASCII 码值ch >= 32 && ch < 127范围内、不包括 $ 的可打印字符。<br /><br /><br />ValueType 取值为 ReferenceHeader 时：<br /><br />可以引用请求头字段中的某一个字段，限制长度限制为 1\~128 个字符，支持小写字母 a\~z、数字、短划线（-）和下划线（_）。 |No|
| **RuleActions.N.RemoveHeaderConfig.Key** | string | 删除的 header 字段名称，目前只能删除以下几个默认配置的字段<br /><br />X-Real-IP、X-Forwarded-For、X-Forwarded-Proto、X-Forwarded-SrcPort |No|
| **RuleActions.N.CorsConfig.AllowOrigin.N** | string | 允许的访问来源列表。支持只配置一个元素*，或配置一个或多个值。<br /><br />单个值必须以http://或者https://开头，后边加一个正确的域名或一级泛域名。（例：http://*.test.abc.example.com）<br />单个值可以不加端口，也可以指定端口，端口范围：1\~65535。<br />最多支持5个值 |No|
| **RuleActions.N.CorsConfig.AllowHeaders.N** | string | 允许跨域的 Header 列表。支持配置为*或配置一个或多个 value 值。<br />单个 value 值只允许包含大小写字母、数字，不能以下划线（_）和短划线（-）开头或结尾，最大长度限制为 32 个字符。<br />最多支持20个值  |No|
| **RuleActions.N.CorsConfig.ExposeHeaders.N** | string | 允许暴露的 Header 列表。支持配置为*或配置一个或多个 value 值。<br />单个 value 值只允许包含大小写字母、数字，不能以下划线（_）和短划线（-）开头或结尾，最大长度限制为 32 个字符。<br />最多支持20个值 |No|
| **RuleActions.N.CorsConfig.AllowMethods.N** | string | 选择跨域访问时允许的 HTTP 方法。取值：<br /><br />GET。<br />POST。<br />PUT。<br />DELETE。<br />HEAD。<br />OPTIONS。<br />PATCH。 |No|
| **RuleActions.N.CorsConfig.AllowCredentials** | string | 是否允许携带凭证信息。取值：<br /><br />on：是。<br />off：否。 |No|
| **RuleActions.N.CorsConfig.MaxAge** | int | 预检请求在浏览器的最大缓存时间，单位：秒。<br /><br />取值范围：-1\~172800。 |No|
| **RuleActions.N.FixedResponseConfig.HttpCode** | int | 返回的 HTTP 响应码，仅支持 2xx、4xx、5xx 数字，x 为任意数字。 |No|
| **RuleActions.N.FixedResponseConfig.Content** | string | 返回的固定内容。最大支持存储 1 KB，只支持 ASCII 码值ch >= 32 && ch < 127范围内、不包括 $ 的可打印字符。 |No|
| **Pass** | boolean | 当转发的服务节点为空时，规则是否忽略。默认转发规则不可更改 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateRuleAttribute
&Region=cn-zj
&ProjectId=fMqGeCGY
&LoadBalancerId=PEmbuMhD
&ListenerId=eudxefBy
&RuleId=uOPZrous
&RuleConditions.n.Type=XPnIhJcD
&RuleConditions.n.HostConfig.MatchMode=pcWuiASR
&RuleConditions.n.HostConfig.Values.n=NbTJIuXo
&RuleConditions.n.PathConfig.Values.n=vXMMFKpU
&RuleActions.n.Type=sCUpJcAT
&RuleActions.n.ForwardConfig.Targets.n.Id=ejIILinH
&RuleActions.n.ForwardConfig.Targets.n.Weight=6
&Pass=true
&RuleActions.n.Order=1
&RuleActions.n.InsertHeaderConfig.Key=iGHrRJXh
&RuleActions.n.InsertHeaderConfig.ValueType=WcdWrLgO
&RuleActions.n.InsertHeaderConfig.Value=UNEDnrWk
&RuleActions.n.RemoveHeaderConfig.Key=CiMITCzA
&RuleActions.n.CorsConfig.AllowOrigin.n=PPXPigPd
&RuleActions.n.CorsConfig.AllowHeaders.n=nkbiBXLo
&RuleActions.n.CorsConfig.ExposeHeaders.n=tpamsjOJ
&RuleActions.n.CorsConfig.AllowMethods.n=mOlPiQPi
&RuleActions.n.CorsConfig.AllowCredentials=oPdIQEiP
&RuleActions.n.CorsConfig.MaxAge=6
&RuleActions.n.FixedResponseConfig.HttpCode=5
&RuleActions.n.FixedResponseConfig.Content=hzFSdYOm
```

### 响应示例
    
```json
{
  "Action": "UpdateRuleAttributeResponse",
  "RetCode": 0
}
```





