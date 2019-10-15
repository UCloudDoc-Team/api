# 获取客户VPN网关信息-DescribeRemoteVPNGateway

获取客户VPN网关信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|RemoteVPNGatewayIds.n|string|客户VPN网关的资源ID，例如RemoteVPNGatewayIds.0代表希望获取客户VPN网关1的信息，RemoteVPNGatewayIds.1代表客户VPN网关2，如果为空，则返回当前Region中所有客户VPN网关实例的信息|No|
|Tag|string|业务组名称，若指定则返回业务组下所有客户VPN网关信息|No|
|Offset|int|数据偏移量, 默认为0|No|
|Limit|int|数据分页值, 默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|符合条件的客户VPN网关总数|No|
|DataSet|array|客户VPN网关列表, 每项参数详见 RemoteVPNGatewayDataSet|No|

## RemoteVPNGatewayDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RemoteVPNGatewayId|string|客户网关ID|No|
|RemoteVPNGatewayName|string|客户网关名称|No|
|RemoteVPNGatewayAddr|string|客户网关IP地址|No|
|Tag|string|用户组|No|
|Remark|string|备注|No|
|CreateTime|int|创建时间|No|
|ActiveTunnels|string|活跃的隧道id|No|
|TunnelCount|int|活跃的隧道数量|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeRemoteVPNGateway
&Region=cn-sh2
&ProjecId=org-XXXX
&RemoteVPNGatewayId= remotevpngw-XXXXX
&Tag=Default
&Offset=1
&Limit=7
```

# Response Example
```
{
    "Action": "DescribeRemoteVPNGatewayResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "TunnelCount": 1, 
            "RemoteVPNGatewayId": "remotevpngw-XXX", 
            "Remark": "test", 
            "RemoteVPNGatewayName": "test", 
            "Tag": "Default", 
            "RemoteVPNGatewayAddr": "1.1.XX.1", 
            "ActiveTunnels": [
                "vpntunnel-XXXX"
            ], 
            "CreateTime": 1530070801
        }
    ]
}
```

