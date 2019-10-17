# 创建云硬盘-CreateUDisk

创建UDisk磁盘

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Size|int|购买UDisk大小,单位:GB,普通盘: 范围[1\~2000], 权限位控制可达8T,若需要请申请开通相关权限;SSD盘： 范围[1\~4000]。|**Yes**|
|Name|string|实例名称|**Yes**|
|ChargeType|string|Year , Month, Dynamic, Postpay, Trial 默认: Dynamic|No|
|Quantity|int|购买时长 默认: 1|No|
|UDataArkMode|string|是否开启数据方舟|No|
|Tag|string|业务组 默认：Default|No|
|DiskType|string|UDisk 类型: DataDisk（普通数据盘），SSDDataDisk（SSD数据盘），RSSDDataDisk（RSSD数据盘），默认值（DataDisk）|No|
|UKmsMode|string|是否加密。Yes：加密，No：不加密，默认值（No）|No|
|CmkId|string|加密需要的cmk id，UKmsMode为Yes时，必填|No|
|CouponId|string|使用的代金券id|No|

?> "17092": "该磁盘版本过低，无法开启数据方舟"

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UDiskId|array|UDisk实例Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUDisk
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=1
&Name=test_udisk
&UKmsMode=nVotfCwC
&UKmsMode=dETGTJcu
&CmkId=QimcSCvt
```

# Response Example
```
{
    "Action": "CreateUDiskResponse", 
    "RetCode": 0, 
    "UDiskId": [
        "bs-xxx"
    ]
}
```

