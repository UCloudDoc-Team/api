# 更新VIP信息-UpdateVIPAttribute

更新VIP信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|VIPId|string|内网VIP的资源Id|**Yes**|
|Remark|string|内网VIP的备注|No|
|Name|string|内网VIP的名称|No|
|Tag|string|内网VIP所属的业务组|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateVIPAttribute
&Region=CAeImjOw
&ProjectId=ileOOloo
&VIPId=MJSsXhyW
&Tag=FewMOtTw
&Remark=GgcHpGTb
&Name=vdHPaBqW
```

# Response Example
```
{
    "Action": "UpdateVIPAttributeResponse", 
    "RetCode": 0
}
```

