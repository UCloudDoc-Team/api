# 获取带宽包信息-DescribeBandwidthPackage

获取某地域下的带宽包信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Limit|int|返回数据分页值, 取值范围为 [0,10000000] 之间的整数, 默认为20|No|
|Offset|int|返回数据偏移量, 默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的带宽包总数|No|
|DataSets|array|带宽包详细信息, 参见 UnetBandwidthPackageSet|No|

## UnetBandwidthPackageSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BandwidthPackageId|string|带宽包的资源ID|No|
|EnableTime|int|生效时间, 格式为 Unix Timestamp|No|
|DisableTime|int|失效时间, 格式为 Unix Timestamp|No|
|CreateTime|int|创建时间, 格式为 Unix Timestamp|No|
|Bandwidth|int|带宽包的临时带宽值, 单位Mbps|No|
|EIPId|string|带宽包所绑定弹性IP的资源ID|No|
|EIPAddr|array|带宽包所绑定弹性IP的详细信息,只有当EIPId对应双线IP时, EIPAddr的长度为2, 其他情况, EIPAddr长度均为1.参见 EIPAddrSet|No|

## EIPAddrSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|OperatorName|string|运营商信息, 枚举值为: Telecom 电信; Unicom: 联通; Duplet: 双线; Bgp: BGP; International: 国际.|**Yes**|
|IP|string|弹性IP地址|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeBandwidthPackage
&Region=cn-bj2
```

# Response Example
```
{
    "Action": "DescribeBandwidthPackageResponse", 
    "TotalCount": 1, 
    "DataSets": [
        {
            "EnableTime": 1430990525, 
            "BandwidthPackageID": "bwpack-XXXXXX", 
            "EIPId": "eip-XXXXX", 
            "EIPAddr": [
                {
                    "IP": "123.59.XX.XX", 
                    "OperatorName": "Bgp"
                }
            ], 
            "Bandwidth": 200, 
            "DisableTime": 1430997725, 
            "CreateTime": 1430990525
        }
    ], 
    "RetCode": 0
}
```

