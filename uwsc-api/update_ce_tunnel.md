# 更新隧道配置 - UpdateCETunnel

## 简介

更新隧道配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateCETunnel)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateCETunnel`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VPNTunnelId** | string | 资源ID |**Yes**|
| **IKEConf.PreSharedKey** | string | IKE 共享密钥 |**Yes**|
| **IKEConf.Version** | string | IKE 版本，取值： "ike v1"，"ike v2" |**Yes**|
| **IKEConf.ExchangeMode** | string | IKE 协商模式，主模式(main)/野蛮模式(aggressive)，IKE V2时不使用该参数 |**Yes**|
| **IKEConf.EncryptionAlgorithm** | string | IKE 加密算法，取值："aes128", "aes192", "aes256", "aes512", "3des" |**Yes**|
| **IKEConf.AuthenticationAlgorithm** | string | IKE 认证算法，取值："md5", "sha1", "sha2-256" |**Yes**|
| **IKEConf.DhGroup** | string | DH group，指定IKE交换密钥时使用的DH组。取值："1", "2", "5", "14", "15", "16" |**Yes**|
| **IKEConf.LocalId** | string | 本端标识，取值：“auto”，“<ip-address>” |**Yes**|
| **IKEConf.RemoteId** | string | 对端标识，取值：“auto”，“<ip-address>” |**Yes**|
| **IKEConf.SALifeTime** | string | IKE SA的生存周期，取值范围：600-604800 |**Yes**|
| **IPSecConf.CENetwork.N** | string | 需要和 VPC 互通的本地数据中心侧的网段，用于第二阶段协商。 |**Yes**|
| **IPSecConf.Protocol** | string | IPSec 安全协议，取值：“esp”，“ah” |**Yes**|
| **IPSecConf.EncryptionAlgorithm** | string | IPSec 加密算法，取值："aes128", "aes192", "aes256", "aes512", "3des" |**Yes**|
| **IPSecConf.AuthenticationAlgorithm** | string | 第二阶段协商的认证算法。取值：md5、sha1、sha2-256。 |**Yes**|
| **IPSecConf.PFSDhGroup** | string | 第二阶段协商使用的 Diffie-Hellman 密钥交换算法。取值：disabled、1、2、5、14、15、16。 |**Yes**|
| **IPSecConf.SALifeTime** | string | 第二阶段协商出的 SA 的生存周期。单位：秒。取值范围：1200\~604800 |**Yes**|
| **IPSecConf.SALifetimeBytes** | string | 第二阶段协商出的 SA 的生存周期。单位：字节 KB。取值范围：8000 – 20000000，默认使用SA超时时间 |No|
| **CloseAction** | string | IPSec 关闭后动作，枚举值：restart、trap、none |No|
| **DPDConf.Enabled** | string | 是否开启 DPD（对等体存活检测）功能。取值：0（关闭）、1（开启） |No|
| **DPDConf.Action** | string | DPD超时后的动作,Enable为1（开启）时有效。可取值为clear（断开）、restart（重试）和 trap（流量触发） |No|
| **DPDConf.Delay** | string | DPD探测间隔时间。dpdEnable为1（开启）时有效。单位为秒，默认为 10 |No|
| **DPDConf.Timeout** | string | DPD超时时间。即探测确认对端不存在需要的时间。dpdEnable为1（开启）时有效。单位为秒。取值范围为 30-60（IKEv2 默认为 0） |No|
| **BGPConf.TunnelCidr** | string | BGP隧道网段。该网段需是一个在 169.254.0.0/16 内的掩码长度为 30 的网段。 |No|
| **BGPConf.LocalAsn** | string | Ucloud侧的自治系统号。 |No|
| **BGPConf.PeerAsn** | string | 对端BGP ASN号。 |No|
| **BGPConf.LocalIp** | string | 云端BGP地址。必须从BGP隧道网段内分配。 |No|
| **BGPConf.PeerIp** | string | 用户端BGP地址。必须从BGP隧道网段内分配。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateCETunnel
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=FMbiUzZs
&VPNTunnelId=dSbEYQFf
&IKEConf=orNmZLvc
&IPSecConf=sAStYCJH
&CloseAction=ioZxlfKH
&BGPConf=ZYDIPESM
&Mode=Nqrjdgyq
&DPDConf=luczSaPu
&IKEConf.Version=diLvEWLr
&IKEConf.ExchangeMode=DXogsrUv
&IKEConf.EncryptionAlgorithm=dxznsFHs
&IKEConf.AuthenticationAlgorithm=avwzsIdv
&IKEConf.DhGroup=GSSTqIxd
&IKEConf.LocalId=dwEGDCJE
&IKEConf.RemoteId=wvRVnWov
&IKEConf.SALifeTime=WJReGHpG
&IPSecConf.CENetwork.N=sXwWHqxV
&IPSecConf.EncryptionAlgorithm=pEQrytMC
&IPSecConf.AuthenticationAlgorithm=owvNXFgv
&IPSecConf.PFSDhGroup=JIWgmZyP
&IPSecConf.SALifeTime=msAnFFGt
&IPSecConf.SALifetimeBytes=TdQZZGJm
&DPDConf.Action=kbZIrpEg
&DPDConf.Delay=MyeUCMAV
&DPDConf.Timeout=EqhvCysu
&BGPConf.LocalAsn=uwTMpspL
&BGPConf.PeerAsn=taMnpTjz
&BGPConf.LocalIp=KYXTeUfW
&BGPConf.PeerIp=cRiUBzyF
```

### 响应示例
    
```json
{
  "Action": "UpdateCETunnelResponse",
  "Message": "fqcBBpSp",
  "RetCode": 0
}
```





