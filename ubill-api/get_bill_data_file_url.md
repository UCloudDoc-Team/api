# 生成账单数据文件下载的 url-GetBillDataFileUrl

生成账单数据文件下载的 url

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BillPeriod|int|账期（时间戳格式）|**Yes**|
|BillType|int|账单类型，传 0 时获取账单总览报表，传 1 获取账单明细报表|**Yes**|
|PaidType|int|获取账单总览报表时，账单的支付状态，传 0 时获取待支付账单，传 1 时获取已支付账单。获取账单明细报表时该参数无效|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|FileUrl|string|交易账单数据下载URL|No|
|IsValid|string|生成的 URL是否有效，即有对应数据文件|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetBillDataFileUrl
&BillPeriod=1542681193
&BillType=0
&PaidType=1
```

# Response Example
```
{
    "Action": "GetBillDataFileUrlResponse", 
    "IsValid": "yes", 
    "FileUrl": "http://pre-channel-1.cn-sh2.ufileos.com/summary-bill-transaction-1-2018-11.xlsx?UCloudPublicKey=dsdaef121dadew23dads2222s&Expires=1553497568&Signature=seadfg3232ssdads1=", 
    "RetCode": 0
}
```

