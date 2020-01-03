# 获取UEDN可用机房列表-DescribeUEdnAvailableIDC

获取UEDN可用机房列表

# Request Parameters

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|IdcList|array|机房列表|No|

## AvailableIdcInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IdcId|string|机房ID|No|
|Name|string|机房名称|No|
|Isp|string|运营商|No|
|Province|string|省份|No|
|City|string|城市|No|
|Type|string|运营商类型：0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUEdnAvailableIDC
```

# Response Example
```
{
    "Action": "DescribeUEdnAvailableIDCResponse", 
    "RetCode": 0, 
    "IdcList": [
        {
            "Province": "hQibpslv", 
            "City": "fihuruud", 
            "Name": "weOTWvdM", 
            "Isp": "wxwbknxZ", 
            "IdcId": "RbisyJSX", 
            "Type": "HQawoRyh"
        }
    ]
}
```

