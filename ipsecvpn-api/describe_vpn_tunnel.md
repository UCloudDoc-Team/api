# 获取VPN隧道信息-DescribeVPNTunnel

获取VPN隧道信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|VPNTunnelIds.n|string|VPN隧道的资源ID，例如VPNTunnelIds.0代表希望获取信息的VPN隧道1，VPNTunneIds.1代表VPN隧道2，如果为空，则返回当前Region中所有的VPN隧道实例|No|
|Offset|int|数据偏移量, 默认为0|No|
|Limit|int|数据分页值, 默认为20|No|
|Tag|string|业务组名称，若指定则返回指定的业务组下的所有VPN网关的信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|VPN隧道总数|No|
|DataSet|array|获取的VPN隧道信息列表，每项参数详见 VPNTunnelDataSet|No|

## VPNTunnelDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|VPNTunnelId|string|隧道id|No|
|VPNTunnelName|string|隧道名称|No|
|Tag|string|用户组|No|
|Remark|string|备注|No|
|VPNGatewayId|string|所属VPN网关id|No|
|RemoteVPNGatewayId|string|对端网关Id|No|
|VPNGatewayName|string|VPN网关名字|No|
|RemoteVPNGatewayName|string|对端网关名字|No|
|VPCId|string|所属VPCId|No|
|VPCName|string|所属VOC名字|No|
|CreateTime|int|创建时间|No|
|IKEData|object|IKE参数|No|
|IPSecData|object|IPSec参数|No|

## IKEData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IKEAuthenticationAlgorithm|string|IKE认证算法|No|
|IKEDhGroup|string|IKEDH组|No|
|IKEEncryptionAlgorithm|string|IKE加密算法|No|
|IKEExchangeMode|string|IKEv1协商模式|No|
|IKELocalId|string|IKE本地ID标识|No|
|IKEPreSharedKey|string|IKE预共享秘钥|No|
|IKERemoteId|string|IKE对端ID标识|No|
|IKESALifetime|string|IKE秘钥生存时间|No|
|IKEVersion|string|IKE版本|No|

## IPSecData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IPSecAuthenticationAlgorithm|string|IPSec通道中使用的认证算法|No|
|IPSecEncryptionAlgorithm|string|IPSec通道中使用的加密算法|No|
|IPSecLocalSubnetIds|array|指定VPN连接的本地子网，用逗号分隔|No|
|IPSecProtocol|string|使用的安全协议，ESP或AH|No|
|IPSecRemoteSubnets|array|指定VPN连接的客户网段，用逗号分隔|No|
|IPSecSALifetime|string|IPSec中SA的生存时间|No|
|IPSecSALifetimeBytes|string|IPSec中SA的生存时间（以字节计）|No|
|IPSecPFSDhGroup|string|是否开启PFS功能,Disable表示关闭，数字表示DH组|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeVPNTunnel
&Region=cn-sh2
&ProjecId=org-XXXX
&VPNTunnelId=vpntunnel-XXXXX
&Offset=3
&Limit=8
```

# Response Example
```
{
    "Action": "DescribeVPNTunnelResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "RemoteVPNGatewayId": "remotevpngw-XXXX", 
            "Remark": "test", 
            "Tag": "Default", 
            "VPCName": "", 
            "IKEData": {
                "IKEExchangeMode": "main", 
                "IKEVersion": "IKE V1", 
                "IKELocalId": "Auto", 
                "IKESALifetime": "86400", 
                "IKEPreSharedKey": "XXXXXX", 
                "IKEDhGroup": "15", 
                "IKERemoteId": "Auto", 
                "IKEEncryptionAlgorithm": "aes128", 
                "IKEAuthenticationAlgorithm": "sha1"
            }, 
            "VPCId": "uvnet-XXX", 
            "VPNTunnelId": "vpntunnel-XXXXX", 
            "RemoteVPNGatewayName": "test", 
            "IPSecData": {
                "IPSecLocalSubnetIds": [
                    "subnet-xoq1z1"
                ], 
                "IPSecPFSDhGroup": "Disable", 
                "IPSecEncryptionAlgorithm": "aes128", 
                "IPSecSALifetimeBytes": "", 
                "IPSecRemoteSubnets": [
                    "1.1.XX.1/24"
                ], 
                "IPSecSALifetime": "3600", 
                "IPSecAuthenticationAlgorithm": "sha1", 
                "IPSecProtocol": "esp"
            }, 
            "VPNGatewayId": "vpngw-XXXX", 
            "VPNGatewayName": "111111", 
            "VPNTunnelName": "test", 
            "VPNTunnelStatus": 0, 
            "CreateTime": 1530071372
        }
    ]
}
```

