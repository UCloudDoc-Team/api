# 获取VPN网关信息-DescribeVPNGateway

获取VPN网关信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|VPNGatewayIds.n|string|VPN网关的资源ID，例如VPNGatewayIds.0代表希望获取VPN网关1的信息，VPNGatewayIds.1代表VPN网关2，如果为空，则返回当前Region中所有VPN网关的信息|No|
|VPCId|string|VPC的资源ID，返回指定的VPC下的所有VPN网关的信息。默认返回当前Region中所有VPN网关实例的信息|No|
|Offset|int|数据偏移量。默认为0|No|
|Tag|string|业务组名称，若指定则返回指定的业务组下的所有VPN网关的信息。|No|
|Limit|int|数据分页值。默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的VPN网关总数|No|
|DataSet|array|获取的VPN网关信息列表，每项参数详见 VPNGatewayDataSet|No|

## VPNGatewayDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|VPNGatewayId|string|网关Id|No|
|VPNGatewayName|string|网关名字|No|
|Tag|string|网关业务组|No|
|Remark|string|网关备注|No|
|VPCId|string|所属VPCId|No|
|VPCName|string|所属VPC名字|No|
|ChargeType|string|付费类型|No|
|CreateTime|int|创建时间|No|
|ExpireTime|int|到期时间|No|
|AutoRenew|string|是否自动续费|No|
|Grade|string|网关类型|No|
|EIP|string|绑定EIP的IP地址|No|
|EIPType|string|EIP类型|No|
|EIPId|string|EIPID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeVPNGateway
&Region=cn-sh2
&ProjecId=org-XXXX
&VPNGatewayId.0=vpngw-XXXX
&VPNGatewayId.1=vpngw-XXXX
&VPCId=uvnet-XXXX
&Offset=2
&Limit=3
&Tag=Default
```

# Response Example
```
{
    "Action": "DescribeVPNGatewayResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "EIP": "106.75.XX.78", 
            "Remark": "", 
            "VPCId": "uvnet-XX", 
            "Grade": "Standard", 
            "VPNGatewayName": "111111", 
            "EIPId": "eip-XX", 
            "ExpireTime": 1530374400, 
            "AutoRenew": "Yes", 
            "Tag": "Default", 
            "VPCName": "", 
            "EIPType": "Bgp", 
            "ChargeType": "Month", 
            "CreateTime": 1530070980, 
            "VPNGatewayId": "vpngw-XXX"
        }
    ]
}
```

