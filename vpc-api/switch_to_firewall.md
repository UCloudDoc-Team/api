# 切换至防火墙模式 - SwitchToFirewall

## 简介

切换至防火墙模式






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=SwitchToFirewall)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SwitchToFirewall`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ResourceId** | string | 资源ID。资源类型为 UHost、UNI、PAAS 资源 |**Yes**|
| **Firewall** | string | 防火墙 ID |No|
| **NodeToFirewall** | string | map[string]string，string 到 防火墙 ID 的映射。ResourceId是uhost则Node是uni；ResourceId是uhadoop则Node是hadoophost |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SwitchToFirewall
&Region=cn-zj
&ProjectId=lLXMWacu
&ResourceId=KOMmrJWL
&IsRemoveFirewall=true
&PrioritySecGroup.n=sJPwMVEC
&UniToPrioritySecGroup=ZDPDfukl
```

### 响应示例
    
```json
{
  "Action": "SwitchToFirewallResponse",
  "Msg": "fxDfOtkW",
  "RetCode": 0
}
```





