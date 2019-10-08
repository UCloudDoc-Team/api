# 获取NAT网关信息-DescribeNATGW

获取NAT网关信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|NATGWIds.n|string|NAT网关Id。默认为该项目下所有NAT网关|No|
|Offset|int|数据偏移量。默认为0|No|
|Limit|int|数据分页值。默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的实例的总数|**Yes**|
|DataSet|array|查到的NATGW信息列表|**Yes**|

## NatGatewayDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NATGWId|string|natgw id|**Yes**|
|NATGWName|string|natgw名称|**Yes**|
|CreateTime|int|natgw创建时间|**Yes**|
|Tag|string|业务组|**Yes**|
|Remark|string|备注|**Yes**|
|FirewallId|string|绑定的防火墙Id|**Yes**|
|VPCId|string|所属VPC Id|**Yes**|
|VPCInfo|string|所属VPC 信息|**Yes**|
|SubnetSet|array|子网 Id|**Yes**|
|IPSet|array|绑定的EIP 信息|**Yes**|
|PolicyId|array|转发策略Id|No|

## NatGatewaySubnetSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SubnetworkId|string|子网id|**Yes**|
|Subnet|string|子网网段|**Yes**|
|SubnetName|string|子网名字|**Yes**|

## NatGatewayIPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|EIPId|string|外网IP的 EIPId|**Yes**|
|Weight|int|权重为100的为出口|**Yes**|
|BandwidthType|string|EIP带宽类型|**Yes**|
|Bandwidth|int|带宽|**Yes**|
|IPResInfo|array|外网IP信息|**Yes**|

## NatGWIPResInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|OperatorName|string|IP的运营商信息|**Yes**|
|EIP|string|外网IP|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeNATGW
&Region=xxx
&ProjectId=xxx
&NATGWIds.0=urIvqFth
&Offset=2
&Limit=8
```

# Response Example
```
{
    "Action": "DescribeNATGWResponse", 
    "TotalCount": 5, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Remark": "", 
            "NATGWName": "nat-spider-test", 
            "IPSet": [
                {
                    "EIPUUID": "eip-kti5zt", 
                    "Weight": 50, 
                    "EIPId": "eip-kti5zt", 
                    "Bandwidth": 1, 
                    "BandwidthType": "Bandwidth", 
                    "IPResInfo": [
                        {
                            "EIP": "106.75.171.117", 
                            "OperatorName": "Bgp"
                        }
                    ]
                }
            ], 
            "VPCName": "vpc-spider-test", 
            "VPCId": "uvnet-4au5pv", 
            "Tag": "Default", 
            "FirewallId": "firewall-fadbay", 
            "PolicyId": [], 
            "SubnetSet": [
                {
                    "SubnetName": "subnet-spider-test", 
                    "Subnet": "192.168.0.0/26", 
                    "SubnetworkId": "subnet-kfi5wu", 
                    "SubnetworkUUID": "subnet-kfi5wu"
                }
            ], 
            "CreateTime": 1541056378, 
            "NATGWId": "natgw-ay4tpe"
        }, 
        {
            "Remark": "", 
            "NATGWName": "xxxxxx", 
            "IPSet": [
                {
                    "EIPUUID": "eip-zqnjjh", 
                    "Weight": 50, 
                    "EIPId": "eip-zqnjjh", 
                    "Bandwidth": 2, 
                    "BandwidthType": "Bandwidth", 
                    "IPResInfo": [
                        {
                            "EIP": "106.75.154.101", 
                            "OperatorName": "Bgp"
                        }
                    ]
                }
            ], 
            "VPCName": "DefaultVPC", 
            "VPCId": "uvnet-cvkbyg", 
            "Tag": "xxxx", 
            "FirewallId": "firewall-fadbay", 
            "PolicyId": [], 
            "SubnetSet": [
                {
                    "SubnetName": "subnet-quyang", 
                    "Subnet": "10.14.128.0/17", 
                    "SubnetworkId": "subnet-t1lhkw", 
                    "SubnetworkUUID": "subnet-t1lhkw"
                }
            ], 
            "CreateTime": 1508817896, 
            "NATGWId": "natgw-d0ubto"
        }, 
        {
            "Remark": "", 
            "NATGWName": "natgw\u5bb9\u707e\u6d4b\u8bd5", 
            "IPSet": [
                {
                    "EIPUUID": "eip-1ir5ot", 
                    "Weight": 50, 
                    "EIPId": "eip-1ir5ot", 
                    "Bandwidth": 1, 
                    "BandwidthType": "Bandwidth", 
                    "IPResInfo": [
                        {
                            "EIP": "106.75.188.86", 
                            "OperatorName": "Bgp"
                        }
                    ]
                }
            ], 
            "VPCName": "\u5bb9\u707e\u6d4b\u8bd511", 
            "VPCId": "uvnet-2b15h0", 
            "Tag": "Default", 
            "FirewallId": "firewall-itqvoh", 
            "PolicyId": [], 
            "SubnetSet": [
                {
                    "SubnetName": "\u5bb9\u707e\u6d4b\u8bd511", 
                    "Subnet": "192.168.128.0/17", 
                    "SubnetworkId": "subnet-jrqoqo", 
                    "SubnetworkUUID": "subnet-jrqoqo"
                }
            ], 
            "CreateTime": 1542097658, 
            "NATGWId": "natgw-frwr22"
        }, 
        {
            "Remark": "", 
            "NATGWName": "abtesst_uxr_natgw_128", 
            "IPSet": [
                {
                    "EIPUUID": "eip-z1pnbo", 
                    "Weight": 50, 
                    "EIPId": "eip-z1pnbo", 
                    "Bandwidth": 2, 
                    "BandwidthType": "Bandwidth", 
                    "IPResInfo": [
                        {
                            "EIP": "106.75.169.103", 
                            "OperatorName": "Bgp"
                        }
                    ]
                }
            ], 
            "VPCName": "abtest_for_uxr", 
            "VPCId": "uvnet-wmrnvj", 
            "Tag": "Default", 
            "FirewallId": "firewall-fadbay", 
            "PolicyId": [], 
            "SubnetSet": [
                {
                    "SubnetName": "abtest_uxr_subnet_128_1", 
                    "Subnet": "10.128.10.0/24", 
                    "SubnetworkId": "subnet-ehkpnt", 
                    "SubnetworkUUID": "subnet-ehkpnt"
                }, 
                {
                    "SubnetName": "abtest_uxr_subnet_128_2", 
                    "Subnet": "10.128.20.0/24", 
                    "SubnetworkId": "subnet-gttjg5", 
                    "SubnetworkUUID": "subnet-gttjg5"
                }
            ], 
            "CreateTime": 1541043690, 
            "NATGWId": "natgw-m1zj4z"
        }, 
        {
            "Remark": "", 
            "NATGWName": "abtest_uxr_natgw_129", 
            "IPSet": [
                {
                    "EIPUUID": "eip-nzkt14", 
                    "Weight": 50, 
                    "EIPId": "eip-nzkt14", 
                    "Bandwidth": 2, 
                    "BandwidthType": "Bandwidth", 
                    "IPResInfo": [
                        {
                            "EIP": "106.75.138.165", 
                            "OperatorName": "Bgp"
                        }
                    ]
                }
            ], 
            "VPCName": "abtest_for_uxr_2", 
            "VPCId": "uvnet-ebh53o", 
            "Tag": "Default", 
            "FirewallId": "firewall-fadbay", 
            "PolicyId": [], 
            "SubnetSet": [
                {
                    "SubnetName": "abtest_uxr_subnet_129", 
                    "Subnet": "10.129.10.0/24", 
                    "SubnetworkId": "subnet-c4vxvi", 
                    "SubnetworkUUID": "subnet-c4vxvi"
                }
            ], 
            "CreateTime": 1541043825, 
            "NATGWId": "natgw-0byxyr"
        }
    ]
}
```

