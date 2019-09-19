#创建硬件隔离组-CreateIsolationGroup

创建硬件隔离组，组内机器严格隔离在不同宿主机上。

#Request Parameters
|Parameter name|Type|Description|Required|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目id|No|
|GroupName|string|硬件隔离组名称。请遵照[[api:uhost-api:specification|字段规范]]设定隔离组名称。|**Yes**|
|Remark|string|备注。请遵照[[api:uhost-api:specification|字段规范]]设定隔离组备注。|No|


#Response Elements
|Parameter name|Type|Description|Required|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|GroupId|string|硬件隔离组id|**Yes**|

#Request Example
```
https://api.ucloud.cn/?Action=CreateIsolationGroup
&Region=cn-zj
&GroupName=SNINkvJp
&Remark=uvgtNeqg
&ProjectId=ceguExuq
```
#Response Example
```
{
    "RetCode": 0,
    "Action": "CreateIsolationGroupResponse",
    "GroupId": "NcVjMEvr"
}
```

{{indexmenu_n>1000}}