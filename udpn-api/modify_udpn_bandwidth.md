# 修改带宽-ModifyUDPNBandwidth

修改带宽值

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UDPNId|string|UDPN Id|**Yes**|
|Bandwidth|int|调整后专线带宽, 单位为Mbps，取值范围为大于等于2且小于等于1000([2-1000])的整数|**Yes**|
|CouponId|string|代金劵 ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyUDPNBandwidth
&Region=cn-bj2
&UDPNId=udpn-l5m15x
&Bandwidth=6

```

# Response Example
```
{
    "Action": "ModifyUDPNBandwidthResponse", 
    "RetCode": 0
}
```

