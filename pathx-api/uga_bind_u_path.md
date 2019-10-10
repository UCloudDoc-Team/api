# UGA绑定UPath-UGABindUPath

UGA绑定UPath

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|UGA ID|**Yes**|
|UPathId|string|加速线路id|**Yes**|
|CouponId|string|代金券|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UGABindUPath
&UGAAId=RaAqOwvF
&UPathId=GAJcDPlh
&CouponId=DVCibwXW
```

# Response Example
```
{
    "Action": "UGABindUPathResponse", 
    "RetCode": 0
}
```

