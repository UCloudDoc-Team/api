# 获取弹性IP信息-DescribeEIP

获取弹性IP信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写|No|
|EIPIds.n|string|弹性IP的资源ID如果为空, 则返回当前 Region中符合条件的的所有EIP|No|
|Offset|int|数据偏移量, 默认为0|No|
|Limit|int|数据分页值, 默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的弹性IP总数|No|
|TotalBandwidth|int|满足条件的弹性IP带宽总和, 单位Mbps|No|
|EIPSet|array|弹性IP列表, 每项参数详见 UnetEIPSet|No|

## UnetEIPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|EIPId|string|弹性IP的资源ID|No|
|Weight|int|外网出口权重, 默认为50, 范围[0-100]|No|
|BandwidthType|int|带宽模式, 枚举值为: 0: 非共享带宽模式, 1: 共享带宽模式|No|
|Bandwidth|int|弹性IP的带宽, 单位为Mbps, 当BandwidthType=1时, 该处显示为共享带宽值. 当BandwidthType=0时, 该处显示这个弹性IP的带宽.|No|
|Status|string|弹性IP的资源绑定状态, 枚举值为: used: 已绑定, free: 未绑定, freeze: 已冻结|No|
|ChargeType|string|付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按小时付费; Trial, 试用. 按小时付费和试用这两种付费模式需要开通权限.|No|
|CreateTime|int|弹性IP的创建时间, 格式为Unix Timestamp|No|
|ExpireTime|int|弹性IP的到期时间, 格式为Unix Timestamp|No|
|Resource|object|弹性IP的详细信息列表, 具体结构见下方 UnetEIPResourceSet|No|
|EIPAddr|array|弹性IP的详细信息列表, 具体结构见下方 UnetEIPAddrSet|No|
|Name|string|弹性IP的名称,缺省值为 "EIP"|No|
|Tag|string|弹性IP的业务组标识, 缺省值为 "Default"|No|
|Remark|string|弹性IP的备注, 缺省值为 ""|No|
|PayMode|string|弹性IP的计费模式, 枚举值为: "Bandwidth", 带宽计费; "Traffic", 流量计费; "ShareBandwidth",共享带宽模式. 默认为 "Bandwidth".|No|
|ShareBandwidthSet|object|共享带宽信息 参见 ShareBandwidthSet|No|
|Expire|bool|弹性IP是否到期|No|

## UnetEIPResourceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceType|string|已绑定的资源类型, 枚举值为: uhost, 云主机；natgw：NAT网关；ulb：负载均衡器；upm: 物理机; hadoophost: 大数据集群;fortresshost：堡垒机；udockhost：容器；udhost：私有专区主机；vpngw：IPSec VPN；ucdr：云灾备；dbaudit：数据库审计，uni：虚拟网卡。|No|
|ResourceName|string|已绑定的资源名称|No|
|ResourceID|string|已绑定资源的资源ID|No|
|SubResourceType|string|资源绑定的虚拟网卡的类型。uni，虚拟网卡。|No|
|SubResourceName|string|资源绑定的虚拟网卡的名称|No|
|SubResourceId|string|资源绑定的虚拟网卡的ID|No|
|EIPId|string|弹性IP的资源ID|No|

## UnetEIPAddrSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|OperatorName|string|运营商信息如: 国际: International, BGP: BGP|No|
|IP|string|IP地址|No|

## ShareBandwidthSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ShareBandwidth|int|共享带宽带宽值|No|
|ShareBandwidthName|string|共享带宽的资源名称|No|
|ShareBandwidthId|string|共享带宽ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeEIP
&Region=cn-bj2
&EIPIds.0=eip-XXXXX
```

# Response Example
```
{
    "RetCode": 0, 
    "TotalBandwidth": 13, 
    "Request_uuid": "f33cf273-89ed-4215-a9c6-XXXXXXX", 
    "TotalCount": 10, 
    "Action": "DescribeEIPResponse", 
    "EIPSet": [
        {
            "Status": "used", 
            "PayMode": "ShareBandwidth", 
            "Remark": "", 
            "Resource": {
                "ResourceType": "uhost", 
                "ResourceID": "uhost-XXXXXX", 
                "Zone": "cn-sh2-01", 
                "ResourceName": "test"
            }, 
            "Name": "EIP", 
            "Weight": 50, 
            "ShareBandwidthSet": {
                "ShareBandwidthName": "test", 
                "ShareBandwidth": 20, 
                "ShareBandwidthId": "bwshare-XXXX"
            }, 
            "EIPId": "eip-XXXXX", 
            "ChargeType": "Month", 
            "ExpireTime": 1530374400, 
            "Expire": false, 
            "Bandwidth": 20, 
            "Tag": "Default", 
            "EIPAddr": [
                {
                    "IP": "106.75.XX.XX", 
                    "OperatorName": "BGP"
                }
            ], 
            "CreateTime": 1528785841, 
            "BandwidthType": 1
        }
    ]
}
```

