# 更新VPN隧道属性-UpdateVPNTunnelAttribute

更新VPN隧道属性

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|VPNTunnelId|string|VPN隧道的资源ID|**Yes**|
|IKEPreSharedKey|string|预共享密钥|No|
|IKEEncryptionAlgorithm|string|IKE协商过程中使用的加密算法|No|
|IKEAuthenticationAlgorithm|string|IKE协商过程中使用的认证算法|No|
|IKEExchangeMode|string|IKE协商过程中使用的模式，可选“主动模式”与“野蛮模式”|No|
|IKELocalId|string|本端标识|No|
|IKERemoteId|string|客户端标识|No|
|IKEDhGroup|string|IKE协商过程中使用的DH组|No|
|IKESALifetime|string|IKE中SA的生存时间|No|
|IPSecProtocol|string|使用的安全协议，ESP或AH|No|
|IPSecLocalSubnetIds.n|string|指定VPN连接的本地子网的id，用逗号分隔|No|
|IPSecRemoteSubnets.n|string|指定VPN连接的客户网段，用逗号分隔|No|
|IPSecEncryptionAlgorithm|string|IPSec隧道中使用的加密算法|No|
|IPSecAuthenticationAlgorithm|string|IPSec隧道中使用的认证算法|No|
|IPSecSALifetime|string|IPSec中SA的生存时间|No|
|IPSecSALifetimeBytes|string|IPSec中SA的生存时间（以字节计）|No|
|IPSecPFSDhGroup|string|IPSec中的PFS是否开启|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateVPNTunnelAttribute
&Region=cn-sh2
&ProjecId=org-XXXX
&VPNTunnelId=vpntunnel-XXXX
&Tag=test
&Remark=test
```

# Response Example
```
{
    "Action": "UpdateVPNTunnelAttributeResponse", 
    "RetCode": 0
}
```

