# 购买配额-BuyUFileQuota（已下线）

购买配额 ——新计费规则已废弃该购买方式，新规则可参考文档：https://docs.ucloud.cn/storage_cdn/ufile/bill

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|QuotaType|string|配额类型，取值为storage-volume, download-traffic或request-count|**Yes**|
|Region|string|配额所属地域，默认为北京|**Yes**|
|Quota|int|配额数值|**Yes**|
|CouponId|string|代金券编号|No|
|ProjectId|string|项目ID|No|

```
QuotaType和Quota参数限制说明如下：
1) storage-volome的单位为GB*天，Quota取值范围为 [100, 30 000 000]，且Quota是100的倍数；
2）download-traffic的单位为GB，Quota取值范围为 [1, 102 400]；
3）request-count的单位为万次，Quota取值范围为 [1, 1 000 000]
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|OrderNumber|string|订单号|No|

# Request Example
```
https://api.ucloud.cn/?Action=BuyUFileQuota
&Region=cn-bj2
&QuotaType=storage-volume
&Quota=100
```
# Response Example
```
{
    "Action": "BuyUFileQuotaResponse",
    "Retcode": 0,
    "OrderNumber": "2015033100171121010"
}
```

