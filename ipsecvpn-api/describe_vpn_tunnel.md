# 获取VPN隧道信息 - DescribeVPNTunnel

## 简介

获取VPN隧道信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeVPNTunnel)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeVPNTunnel`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **VPNTunnelIds.N** | string | VPN隧道的资源ID，例如VPNTunnelIds.0代表希望获取信息的VPN隧道1，VPNTunneIds.1代表VPN隧道2，如果为空，则返回当前Region中所有的VPN隧道实例 |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 数据分页值, 默认为20 |No|
| **Tag** | string | 业务组名称，若指定则返回指定的业务组下的所有VPN网关的信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | VPN隧道总数 |No|
| **DataSet** | array[[*VPNTunnelDataSet*](#VPNTunnelDataSet)] | 获取的VPN隧道信息列表，每项参数详见 VPNTunnelDataSet |No|

#### 数据模型


#### VPNTunnelDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VPNTunnelId** | string | 隧道id |No|
| **VPNTunnelName** | string | 隧道名称 |No|
| **Tag** | string | 用户组 |No|
| **Remark** | string | 备注 |No|
| **VPNGatewayId** | string | 所属VPN网关id |No|
| **RemoteVPNGatewayId** | string | 对端网关Id |No|
| **VPNGatewayName** | string | VPN网关名字 |No|
| **RemoteVPNGatewayName** | string | 对端网关名字 |No|
| **VPCId** | string | 所属VPCId |No|
| **VPCName** | string | 所属VOC名字 |No|
| **CreateTime** | int | 创建时间 |No|
| **IKEData** | [*IKEData*](#IKEData) | IKE参数 |No|
| **IPSecData** | [*IPSecData*](#IPSecData) | IPSec参数 |No|

#### IKEData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IKEAuthenticationAlgorithm** | string | IKE认证算法 |No|
| **IKEDhGroup** | string | IKEDH组 |No|
| **IKEEncryptionAlgorithm** | string | IKE加密算法 |No|
| **IKEExchangeMode** | string | IKEv1协商模式 |No|
| **IKELocalId** | string | IKE本地ID标识 |No|
| **IKEPreSharedKey** | string | IKE预共享秘钥 |No|
| **IKERemoteId** | string | IKE对端ID标识 |No|
| **IKESALifetime** | string | IKE秘钥生存时间 |No|
| **IKEVersion** | string | IKE版本 |No|

#### IPSecData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IPSecAuthenticationAlgorithm** | string | IPSec通道中使用的认证算法 |No|
| **IPSecEncryptionAlgorithm** | string | IPSec通道中使用的加密算法 |No|
| **IPSecLocalSubnetIds** | array[string] | 指定VPN连接的本地子网，用逗号分隔 |No|
| **IPSecProtocol** | string | 使用的安全协议，ESP或AH |No|
| **IPSecRemoteSubnets** | array[string] | 指定VPN连接的客户网段，用逗号分隔 |No|
| **IPSecSALifetime** | string | IPSec中SA的生存时间 |No|
| **IPSecSALifetimeBytes** | string | IPSec中SA的生存时间（以字节计） |No|
| **IPSecPFSDhGroup** | string | 是否开启PFS功能,Disable表示关闭，数字表示DH组 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeVPNTunnel
&Region=cn-sh2
&ProjecId=org-XXXX
&VPNTunnelId=vpntunnel-XXXXX
&Offset=3
&Limit=8
```

### 响应示例
    
```json
{
  "Action": "DescribeVPNTunnelResponse",
  "DataSet": [
    {
      "CreateTime": 1530071372,
      "IKEData": {
        "IKEAuthenticationAlgorithm": "sha1",
        "IKEDhGroup": "15",
        "IKEEncryptionAlgorithm": "aes128",
        "IKEExchangeMode": "main",
        "IKELocalId": "Auto",
        "IKEPreSharedKey": "XXXXXX",
        "IKERemoteId": "Auto",
        "IKESALifetime": "86400",
        "IKEVersion": "IKE V1"
      },
      "IPSecData": {
        "IPSecAuthenticationAlgorithm": "sha1",
        "IPSecEncryptionAlgorithm": "aes128",
        "IPSecLocalSubnetIds": [
          "subnet-xoq1z1"
        ],
        "IPSecPFSDhGroup": "Disable",
        "IPSecProtocol": "esp",
        "IPSecRemoteSubnets": [
          "1.1.XX.1/24"
        ],
        "IPSecSALifetime": "3600",
        "IPSecSALifetimeBytes": ""
      },
      "Remark": "test",
      "RemoteVPNGatewayId": "remotevpngw-XXXX",
      "RemoteVPNGatewayName": "test",
      "Tag": "Default",
      "VPCId": "uvnet-XXX",
      "VPCName": "",
      "VPNGatewayId": "vpngw-XXXX",
      "VPNGatewayName": "111111",
      "VPNTunnelId": "vpntunnel-XXXXX",
      "VPNTunnelName": "test",
      "VPNTunnelStatus": 0
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





