# 普通升级为方舟机型-UpgradeToArkUHostInstance

普通升级为方舟机型

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|UHostIds.n|string|UHost主机的资源ID，例如UHostIds.0代表希望升级的主机1，UHostIds.1代表主机2。|**Yes**|
|CouponId|string|代金券ID 请参考DescribeCoupon接口|No|

```
升级注意事项：仅支持普通型+本地盘的组合，需要关机进行，且整个升级过程较慢，每100G约需要等待30分钟。
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UHostSet|array|UHost主机的资源ID数组|No|

# Request Example
```
https://api.ucloud.cn/?Action=UpgradeToArkUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostIds.0=uhost-xxx
```

# Response Example
```
{
    "Action": "UpgradeToArkUHostInstanceResponse", 
    "RetCode": 0, 
    "UHostSet": [
        "uhost-xxx"
    ]
}
```

