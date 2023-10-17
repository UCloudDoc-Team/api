# 创建应用型负载均衡监听器 - CreateListener

## 简介

创建一个应用型负载均衡的监听器






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateListener)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateListener`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **LoadBalancerId** | string | 负载均衡实例的ID |**Yes**|
| **Name** | string | 监听器的名称。限定字符长度：[1-255]；限定特殊字符，仅支持：“-”，“_”，“.”；默认值：listener |No|
| **Remark** | string | 监听器的备注信息。限定字符长度：[0-255] |No|
| **ListenerPort** | int | 监听器的监听端口。应用型限定取值：[1-65535]，默认值80 |No|
| **ListenerProtocol** | string | 监听协议。应用型限定取值：“HTTP”/"HTTPS"，默认值“HTTP” |No|
| **Certificates.N** | string | （应用型专用）服务器默认证书ID。仅HTTPS监听支持，且必填；暂时只支持最大长度为1 |No|
| **SecurityPolicyId** | string | （应用型专用）安全策略组ID。仅HTTPS监听支持绑定；默认值“Default”，表示绑定原生策略 |No|
| **IdleTimeout** | int | 连接空闲超时时间。单位：秒。应用型限定取值：[1-86400]；默认值60 |No|
| **Scheduler** | string | 负载均衡算法。应用型限定取值："Roundrobin"/"Source"/"WeightRoundrobin"/" Leastconn"/"Backup"，默认值"Roundrobin" |No|
| **StickinessConfig.Enabled** | boolean | 是否开启会话保持功能。应用型负载均衡实例基于Cookie实现；默认值为：false |No|
| **StickinessConfig.Type** | string | （应用型专用）Cookie处理方式。限定枚举值："ServerInsert" / "UserDefined"；默认值为：“ServerInsert” |No|
| **StickinessConfig.CookieName** | string | （应用型专用）自定义Cookie。当StickinessType取值"UserDefined"时有效；限定字符长度：[0-255] |No|
| **HealthCheckConfig.Enabled** | boolean | 是否开启健康检查功能。暂时不支持关闭。默认值为：true |No|
| **HealthCheckConfig.Type** | string | 健康检查方式。应用型限定取值：“Port”/"HTTP"，默认值：“Port” |No|
| **HealthCheckConfig.Domain** | string | （应用型专用）HTTP检查域名 |No|
| **HealthCheckConfig.Path** | string | （应用型专用）HTTP检查路径 |No|
| **CompressionEnabled** | boolean | （应用型专用）是否开启数据压缩功能。目前只支持使用gzip对特定文件类型进行压缩。默认值为：false |No|
| **HTTP2Enabled** | boolean | （应用型专用）是否开启HTTP/2特性。仅HTTPS监听支持开启；默认值为：false |No|
| **RedirectEnabled** | boolean | （应用型专用）是否开启HTTP重定向到HTTPS。仅HTTP监听支持开启；默认值为：false |No|
| **RedirectPort** | int | （应用型专用）重定向端口。限定取值：[1-65535]，默认值443 |No|

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
https://api.ucloud.cn/?Action=CreateListener
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=uvNplLqt
&LoadBalancerId=TrMQMxgz
&Name=kHEiMUtI
&Remark=VHkpyFlw
&ListenPort=3
&ListenProtocol=OjJEdAaO
&Certificates.n=WuscVHDW
&SecurityPolicyId=zwsYdamE
&IdleTimeout=3
&Scheduler=lHorTbNl
&StickinessConfig.Enabled=false
&StickinessConfig.Type=fuuciPzx
&StickinessConfig.CookieName=TnXwVeSq
&HealthCheckConfig.Enabled=true
&HealthCheckConfig.Type=pDlMtNon
&HealthCheckConfig.Domain=TWoxQhFA
&HealthCheckConfig.Path=KnPWkCVd
&CompressionEnabled=false
&HTTP2Enabled=false
&RedirectEnabled=false
&RedirectPort=1
```

### 响应示例
    
```json
{
  "Action": "CreateListenerResponse",
  "ListenerId": "pCtZUlZc",
  "RetCode": 0
}
```





