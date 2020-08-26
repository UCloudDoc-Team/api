# 创建VPN隧道 - CreateVPNTunnel

## 简介

创建VPN隧道






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateVPNTunnel)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateVPNTunnel`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **VPNTunnelName** | string | VPN隧道名称 |**Yes**|
| **VPNGatewayId** | string | VPN网关的资源ID |**Yes**|
| **RemoteVPNGatewayId** | string | 客户VPN网关的资源ID |**Yes**|
| **IKEPreSharedKey** | string | 预共享密钥 |**Yes**|
| **VPCId** | string | vpcId |**Yes**|
| **IPSecLocalSubnetIds.N** | string | 指定VPN连接的本地子网的资源ID，最多可填写10个。 |**Yes**|
| **IPSecRemoteSubnets.N** | string | 指定VPN连接的客户网段，最多可填写20个。 |**Yes**|
| **IKEVersion** | string | ike版本，枚举值： "IKE V1"，"IKE V2"，默认v1 |**Yes**|
| **Tag** | string | 业务组，默认为“Default” |No|
| **Remark** | string | 备注，默认为空 |No|
| **IKEEncryptionAlgorithm** | string | IKE协商过程中使用的加密算法，枚举值，"aes128", "aes192", "aes256", "aes512", "3des"。默认值为“aes128” |No|
| **IKEAuthenticationAlgorithm** | string | IKE协商过程中使用的认证算法，"md5", "sha1", "sha2-256"。默认值为“sha1” |No|
| **IKEExchangeMode** | string | IKE协商过程中使用的模式，枚举值，主模式，“main”；野蛮模式，“aggressive”。IKEV1默认为主模式“main”，IKEV2时不使用该参数。 |No|
| **IKELocalId** | string | 本端标识。枚举值，自动识别，“auto”；IP地址或域名。默认为自动识别“auto”。IKEV2必填该参数 |No|
| **IKERemoteId** | string | 客户端标识。枚举值，自动识别，“auto”；IP地址或域名。默认为“自动识别“auto”。IKEV2必填该参数 |No|
| **IKEDhGroup** | string | IKE协商过程中使用的DH组，枚举值，"1", "2", "5", "14", "15", "16"。默认为“15” |No|
| **IKESALifetime** | string | IKE中SA的生存时间，可填写范围为600-604800。默认为86400。 |No|
| **IPSecProtocol** | string | 使用的安全协议，枚举值，“esp”，“ah”。默认为“esp” |No|
| **IPSecEncryptionAlgorithm** | string | IPSec隧道中使用的加密算法，枚举值，"aes128", "aes192", "aes256", "aes512", "3des"。默认值为“aes128” |No|
| **IPSecAuthenticationAlgorithm** | string | IPSec隧道中使用的认证算法，枚举值，"md5", "sha1"。默认值为“sha1” |No|
| **IPSecSALifetime** | string | IPSec中SA的生存时间，可填写范围为1200 - 604800。默认为3600 |No|
| **IPSecSALifetimeBytes** | string | IPSec中SA的生存时间（以字节计）。可选为8000 – 20000000。默认使用SA生存时间， |No|
| **IPSecPFSDhGroup** | string | IPSec的PFS是否开启，枚举值，，不开启，"disable"；数字表示DH组, "1", "2", "5", "14", "15", "16"。默认为“disable”。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **VPNTunnelId** | string | VPN隧道的资源ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateVPNTunnel
&Region=cn-sh2
&ProjectId=org-XXXXX
&VPNTunnelName=test
&Tag=test
&Remark=test
&VPNGatewayId=vpngw-XXXX
&RemoteVPNGatewayId=remotevpngw-XXXX
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
&IPSecPFSDhGroup=disable
&IKEVersion=BXVWyidt
```

### 响应示例
    
```json
{
  "Action": "CreateVPNTunnelResponse",
  "RetCode": 0,
  "VPNTunnelId": "vpntunnel-XXXXXX"
}
```





