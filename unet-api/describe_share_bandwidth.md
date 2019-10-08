# 获取共享带宽信息-DescribeShareBandwidth

获取共享带宽信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ShareBandwidthIds.n|string|需要返回的共享带宽Id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|共享带宽信息组 参见 UnetShareBandwidthSet|No|
|TotalCount|int|符合条件的共享带宽总数，大于等于返回DataSet长度|No|

## UnetShareBandwidthSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IPVersion|string|共享带宽类型|**Yes**|
|ShareBandwidth|int|共享带宽值(预付费)/共享带宽峰值(后付费), 单位Mbps|No|
|ShareBandwidthId|string|共享带宽的资源ID|No|
|ChargeType|string|付费方式, 预付费:Year 按年,Month 按月,Dynamic 按需;后付费:PostPay(按月)|No|
|CreateTime|int|创建时间, 格式为Unix Timestamp|No|
|ExpireTime|int|过期时间, 格式为Unix Timestamp|No|
|EIPSet|array|EIP信息,详情见 EIPSetData|No|
|BandwidthGuarantee|int|共享带宽保底值(后付费)|No|
|PostPayStartTime|int|共享带宽后付费开始计费时间(后付费)|No|
|Name|string|共享带宽名称|No|

## EIPSetData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Bandwidth|int|EIP带宽值|No|
|EIPAddr|array|EIP的IP信息，详情见EIPAddrSet|No|
|EIPId|string|EIP资源Id|No|

## EIPAddrSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|OperatorName|string|运营商信息, 枚举值为: Telecom 电信; Unicom: 联通; Duplet: 双线; Bgp: BGP; International: 国际.|**Yes**|
|IP|string|弹性IP地址|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeShareBandwidth
&Region=cn-bj2
```

# Response Example
```
{
    "Request_uuid": "a36b7aec-3911-4096-9110-XXXXX", 
    "RetCode": 0, 
    "TotolCount": 2, 
    "DataSet": [
        {
            "Name": "test", 
            "ShareBandwidth": 20, 
            "ShareBandwidthId": "bwshare-XXXX", 
            "ExpireTime": 1529898027, 
            "ChargeType": "Dynamic", 
            "EIPSet": [
                {
                    "EIPAddr": [
                        {
                            "IP": "106.75.XX.XX", 
                            "OperatorName": "BGP"
                        }
                    ], 
                    "Bandwidth": 1000, 
                    "EIPId": "eip-XXXXX"
                }
            ], 
            "CreateTime": 1529660427
        }
    ], 
    "TotalCount": 1, 
    "Action": "DescribeShareBandwidthResponse"
}
```

