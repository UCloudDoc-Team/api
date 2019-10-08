# 更改物理机信息-ModifyPHostInfo

更改物理机信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|PHostId|string|物理机资源ID|**Yes**|
|Name|string|物理机名称，默认不更改|No|
|Remark|string|物理机备注，默认不更改|No|
|Tag|string|业务组，默认不更改|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PHostId|string|PHost 的资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action= ModifyPHostInfo
&Region=cn-bj2
&Zone=cn-bj2-04
&projectId=562
&PHostId=upm-oaix4s
&Name=other
```

# Response Example
```
{
    "Action": "ModifyPHostInfoResponse", 
    "PHostId": "upm-oaix4s", 
    "RetCode": 0
}
```

