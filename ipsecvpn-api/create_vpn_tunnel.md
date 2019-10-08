# 创建VPN隧道-CreateVPNTunnel

创建VPN隧道

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|VPNTunnelName|string|VPN隧道名称|**Yes**|
|VPNGatewayId|string|VPN网关的资源ID|**Yes**|
|RemoteVPNGatewayId|string|客户VPN网关的资源ID|**Yes**|
|IKEPreSharedKey|string|预共享密钥|**Yes**|
|VPCId|string|vpcId|**Yes**|
|IPSecLocalSubnetIds.n|string|指定VPN连接的本地子网的资源ID，最多可填写10个。|**Yes**|
|IPSecRemoteSubnets.n|string|指定VPN连接的客户网段，最多可填写20个。|**Yes**|
|Tag|string|业务组，默认为“Default”|No|
|Remark|string|备注，默认为空|No|
|IKEEncryptionAlgorithm|string|IKE协商过程中使用的加密算法|No|
|IKEAuthenticationAlgorithm|string|IKE协商过程中使用的认证算法|No|
|IKEExchangeMode|string|IKE协商过程中使用的模式，可选“主动模式”与“野蛮模式”|No|
|IKELocalId|string|本端标识|No|
|IKERemoteId|string|客户端标识|No|
|IKEDhGroup|string|IKE协商过程中使用的DH组|No|
|IKESALifetime|string|IKE中SA的生存时间|No|
|IPSecProtocol|string|使用的安全协议，ESP或AH|No|
|IPSecEncryptionAlgorithm|string|IPSec隧道中使用的加密算法|No|
|IPSecAuthenticationAlgorithm|string|IPSec隧道中使用的认证算法|No|
|IPSecSALifetime|string|IPSec中SA的生存时间|No|
|IPSecSALifetimeBytes|string|IPSec中SA的生存时间（以字节计）|No|
|IPSecPFSDhGroup|string|IPSec的PFS是否开启|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|VPNTunnelId|string|VPN隧道的资源ID|No|

# Request Example
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
```

# Response Example
```
{
    "Action": "CreateVPNTunnelResponse", 
    "RetCode": 0, 
    "VPNTunnelId": "vpntunnel-XXXXXX"
}
```

