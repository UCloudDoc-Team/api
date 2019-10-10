# 获取云硬盘价格-DescribeUDiskPrice

获取UDisk实例价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Size|int|购买UDisk大小,单位:GB,范围[1~1000]|**Yes**|
|ChargeType|string|Year , Month, Dynamic，Postpay，Trial 默认: Dynamic|No|
|Quantity|int|购买UDisk的时长，默认值为1|No|
|UDataArkMode|string|是否打开数据方舟, 打开"Yes",关闭"No", 默认关闭|No|
|DiskType|string|UDisk 类型: DataDisk（普通数据盘），SSDDataDisk（SSD数据盘），SystemDisk（普通系统盘），SSDSystemDisk（SSD系统盘），RSSDDataDisk（RSSD数据盘），默认值（DataDisk）|No|
|IsTotalPrice|string|是否将数据方舟，云硬盘放入一张订单, 是："Yes",否："No"，默认是"No"|No|
|MachineType|string|云主机机型（V2.0），枚举值["N", "C", "G", "O", "OM"]。参考[云主机机型说明](api/uhost-api/uhost_type)。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|价格参数列表，具体说明见 UDiskPriceDataSet|No|

## UDiskPriceDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|Year， Month， Dynamic，Trial|No|
|Price|int|实际价格 (单位: 分)|No|
|ChargeName|string|"UDataArk","UDisk","Total"|No|
|OriginalPrice|int|用户折后价(对应计费CustomPrice)|No|
|ListPrice|int|原价(对应计费OriginalPrice)|No|

# Request Example
```
https://api.ucloud.cn/udisk/?Action=DescribeUDiskPrice
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&Size=1   
&ChargeType=Month   
&Quantity=12
&UDataArkMode=Yes
&IsTotalPrice=YdLeYNzn
&MachineType=pQoolJSR
```

# Response Example
```
{
    "Action": "DescribeUDiskPriceResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Price": 1360, 
            "ChargeType": "Month", 
            "ChargeName": "UDisk"
        }
    ]
}
```

