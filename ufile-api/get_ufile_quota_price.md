# 查询配额支付价格-GetUFileQuotaPrice

根据UFile的购买配额，查询需要支付的价格。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|StorageVolume|int|存储容量，单位: GB*天，范围: [0, 30 000 000]，步长：100GB*天|No|
|DownloadTraffic|int|下载流量，单位: GB，范围: [0, 60 000]，步长：1GB|No|
|RequestCount|int|请求次数，单位：万次，范围：[0, 1 000 000]，步长：1万次|No|

```
说明：如果StorageVolume > 0，必须保证StorageVolume是100的倍数。
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|float|待支付价格，单位：分|No|

# Request Example
```
https://api.ucloud.cn/uhost/?Action=GetUFileQuotaPrice
&Region=cn-bj2
&StorageVolume=200
&DownloadTraffic=5
&RequestCount=2
```

# Response Example
```
{
    "Action": "GetUFileQuotaPriceResponse", 
    "Price": 346, 
    "RetCode": 0
}
```

