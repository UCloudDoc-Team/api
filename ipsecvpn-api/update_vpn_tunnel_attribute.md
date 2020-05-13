# 更新VPN隧道属性 - UpdateVPNTunnelAttribute

## 简介

更新VPN隧道属性





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateVPNTunnelAttribute)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateVPNTunnelAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **VPNTunnelId** | string | VPN隧道的资源ID |**Yes**|
| **IKEPreSharedKey** | string | 预共享密钥 |No|
| **IKEEncryptionAlgorithm** | string | IKE协商过程中使用的加密算法 |No|
| **IKEAuthenticationAlgorithm** | string | IKE协商过程中使用的认证算法 |No|
| **IKEExchangeMode** | string | IKE协商过程中使用的模式，可选“主动模式”与“野蛮模式”。IKEV2不使用该参数。 |No|
| **IKELocalId** | string | 本端标识。不填时默认使用之前的参数，结合IKEversion进行校验，IKEV2时不能为auto。 |No|
| **IKERemoteId** | string | 客户端标识。不填时默认使用之前的参数，结合IKEversion进行校验，IKEV2时不能为auto。 |No|
| **IKEDhGroup** | string | IKE协商过程中使用的DH组 |No|
| **IKESALifetime** | string | IKE中SA的生存时间 |No|
| **IPSecProtocol** | string | 使用的安全协议，ESP或AH |No|
| **IPSecLocalSubnetIds.N** | string | 指定VPN连接的本地子网的id，用逗号分隔 |No|
| **IPSecRemoteSubnets.N** | string | 指定VPN连接的客户网段，用逗号分隔 |No|
| **IPSecEncryptionAlgorithm** | string | IPSec隧道中使用的加密算法 |No|
| **IPSecAuthenticationAlgorithm** | string | IPSec隧道中使用的认证算法 |No|
| **IPSecSALifetime** | string | IPSec中SA的生存时间 |No|
| **IPSecSALifetimeBytes** | string | IPSec中SA的生存时间（以字节计） |No|
| **IPSecPFSDhGroup** | string | IPSec中的PFS是否开启 |No|
| **IKEVersion** | string | 枚举值："IKE V1","IKE V2" |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateVPNTunnelAttribute
&Region=cn-sh2
&ProjecId=org-XXXX
&VPNTunnelId=vpntunnel-XXXX
&Tag=test
&Remark=test
&VPNTunnelId=vpntunnel-XXXX
&IPSecLocalSubnetIds.0=subnet-XXXX
&IPSecRemoteSubnets.0=1.1.1.1/24
&IKEPreSharedKey=12345
&IKEEncryptionAlgorithm=aes128
&IKEAuthenticationAlgorithm=sha1
&IKEExchangeMode=main
&IKELocalId=auto
&IKERemoteId=auto
&IKEDhGroup=15
&IKESALifetime=86400
&IPSecProtocol=esp
&IPSecLocalSubnetIds=true
&IPSecRemoteSubnets=true
&IPSecEncryptionAlgorithm=aes128
&IPSecAuthenticationAlgorithm=sha1
&IPSecSALifetime=3600
&IPSecSALifetimeBytes=100
&IPSecPFSDhGroup=2
&IKEVersion=lNnYNjjo
```

### 响应示例
    
```json
{
  "Action": "UpdateVPNTunnelAttributeResponse",
  "RetCode": 0
}
```





