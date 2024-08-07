# 创建监听器 - CreateNLBListener

## 简介

创建监听器






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateNLBListener)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateNLBListener`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NLBId** | string | 负载均衡实例的ID |**Yes**|
| **Name** | string | 监听器的名称<br />限定字符长度：[1-255]<br />限定特殊字符，仅支持：-_.<br />默认值：listener |No|
| **Remark** | string | 监听器的备注信息<br />限定字符长度：[0-255] |No|
| **StartPort** | int | 端口范围的起始端口<br />限定取值：[1-65535]<br />默认值 1 |No|
| **EndPort** | int | 端口范围的结束端口<br />限定取值：[1-65535]<br />取值不小于起始端口<br />默认值 65535 |No|
| **Protocol** | string | 监听协议<br />限定取值："TCP"/"UDP" |No|
| **Scheduler** | string | 负载均衡算法<br />限定取值："RoundRobin"/"SourceHash"/"LeastConn"/"WeightLeastConn "/"WeightRoundRobin"<br />默认值 "RoundRobin"  |No|
| **StickinessTimeout** | int | 会话保持超时时间。单位：秒<br />限定取值：[60-900]，0 表示不开启会话保持<br />默认值60 |No|
| **HealthCheckConfig.Enabled** | boolean | 是否开启健康检查功能。暂时不支持关闭，默认 true |No|
| **HealthCheckConfig.Port** | int | 健康检查探测端口 说明： 限定取值：[1-65535] |No|
| **HealthCheckConfig.Type** | string | 健康检查方式 限定取值："Port"/"UDP"/"Ping" 默认值：“Port” |No|
| **HealthCheckConfig.ReqMsg** | string | UDP" 检查模式的请求字符串 |No|
| **HealthCheckConfig.ResMsg** | string | "UDP" 检查模式的预期响应字符串 |No|
| **ForwardSrcIPMethod** | string | 传递源 IP 方法。<br />限定取值："" / "None" / "Toa"，空字符串和 None 代表关闭。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ListenerId** | string | 监听器的ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateNLBListener
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=MARULUOv
&NLBId=GNvXptgc
&Name=LtMcdpyQ
&Remark=urkacxDK
&StartPort=5
&EndPort=4
&Protocol=vfTQAfIi
&Scheduler=mYCNnjfx
&StickinessTimeout=7
&HealthCheckConfig=WHmazuVn
&HealthCheckConfig.Port=7
&HealthCheckConfig.Type=OTsPFkqI
&HealthCheckConfig.Interval=3
&HealthCheckConfig.MinSuccess=8
&HealthCheckConfig.MaxFail=5
&HealthCheckConfig.ReqMsg=AQIXJQZS
&HealthCheckConfig.ResMsg=bBBpmaEy
&ForwardSrcIPMethod=aRYJWQFx
```

### 响应示例
    
```json
{
  "Action": "CreateNLBListenerResponse",
  "ListenerId": "WVmnGcQN",
  "RetCode": 0
}
```





