# 创建UPath-CreateUPath

创建UPath

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|Name|string|UPath名字|**Yes**|
|LineId|string|线路Id|**Yes**|
|Bandwidth|int|UPath带宽|**Yes**|
|ChargeType|string|计费模式|**Yes**|
|Quantity|string|购买周期|**Yes**|
|CouponId|string|代金券Id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UPathId|string|加速线路Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUPath
&Name=FfIhKqqo
&LineId=qdMMXHWa
&Bandwidth=7
&ChargeType=Year
&Quantity=wapGDWAQ
&CouponId=JvqLdhxW
```

# Response Example
```
{
    "PathId": "RFbySLFA", 
    "Action": "CreateUPathResponse", 
    "RetCode": 0
}
```

