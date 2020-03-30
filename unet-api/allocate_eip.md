# 申请弹性IP-AllocateEIP

根据提供信息, 申请弹性IP

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 |No|
|OperatorName|string|弹性IP的线路如下: 国际: International BGP: Bgp  各地域允许的线路参数如下:  cn-sh1: Bgp cn-sh2: Bgp cn-gd: Bgp cn-bj1: Bgp cn-bj2: Bgp hk: International us-ca: International th-bkk: International  kr-seoul:International  us-ws:International  ge-fra:International  sg:International  tw-kh:International.其他海外线路均为 International|**Yes**|
|Bandwidth|int|弹性IP的外网带宽, 单位为Mbps. 共享带宽模式必须指定0M带宽, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-200]，带宽计费[1-10000]|**Yes**|
|Tag|string|业务组名称, 默认为 "Default"|No|
|ChargeType|string|付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按需付费(需开启权限); Trial, 试用(需开启权限) 默认为按月付费|No|
|Quantity|int|购买的时长, 默认: 1|No|
|PayMode|string|弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. 默认为 "Bandwidth".“PostAccurateBandwidth”：带宽后付费模式|No|
|ShareBandwidthId|string|绑定的共享带宽Id,仅当PayMode为ShareBandwidth时有效|No|
|Name|string|弹性IP的名称, 默认为 "EIP"|No|
|Remark|string|弹性IP的备注, 默认为空|No|
|CouponId|string|代金券ID, 默认不使用|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|EIPSet|array|申请到的EIP资源详情 参见 UnetAllocateEIPSet|No|

## UnetAllocateEIPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|EIPId|string|申请到的EIP资源ID|No|
|EIPAddr|array|申请到的IPv4地址. |No|

## UnetEIPAddrSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|OperatorName|string|运营商信息如: 国际: International, BGP: BGP|No|
|IP|string|IP地址|No|

# Request Example
```
https://api.ucloud.cn/?Action=AllocateEIP
&Bandwidth=2
&Tag=test
&PayMode=Bandwidth
&OperatorName=Bgp
&ChargeType=Month
&Region=cn-bj2
&UseType=GbJSTTUJ
```

# Response Example
```
{
    "Action": "AllocateEIPResponse", 
    "EIPSet": [
        {
            "EIPAddr": [
                {
                    "IP": "123.55.55.55", 
                    "OperatorName": "BGP"
                }
            ], 
            "EIPId": "eip-nthrdr"
        }
    ], 
    "RetCode": "0"
}
```

