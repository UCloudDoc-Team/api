# 释放弹性IP-ReleaseEIP

释放弹性IP资源, 所释放弹性IP必须为非绑定状态.

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|EIPId|string|弹性IP的资源ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
http://internal.api.ucloud.cn
{
	"Backend":"UNETFE-INTERNAL",
	"Action":"ReleaseEIP",
	"channel":1,
	"az_group":1000001,
	"top_organization_id":50606263,
	"organization_id":50606469,
	"EIPId":"eip-dgftkg"
}
```

# Response Example
```
{
    "Action": "ReleaseEIPResponse", 
    "Request_uuid": "", 
    "RetCode": 0
}
```

