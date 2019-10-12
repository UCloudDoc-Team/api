# UGA绑定UPath-UGABindUPath

UGA绑定UPath

```
绑定线路成功后，加速配置通常会在1min内生效。请先使用nc或telnet命令探测加速域名 加速端口是否联通。正常联通后将业务域名CName到加速域名上来。
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|加速配置实例ID，格式uga-xxxx|**Yes**|
|UPathId|string|加速线路实例ID，格式upath-xxx|**Yes**|
|CouponId|string|代金券|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UGABindUPath
&ProjectId=org-xxxx
&UGAId=uga-xxxx
&UPathId=upath-xxx
&CouponId=
```

# Response Example
```
{
    "Action": "UGABindUPathResponse", 
    "RetCode": 0
}
```

