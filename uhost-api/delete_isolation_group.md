#删除硬件隔离组-DeleteIsolationGroup

删除硬件隔离组（删除隔离组后，组内主机不会被删除）。

#Request Parameters
|Parameter name|Type|Description|Required|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目id|No|
|GroupId|string|硬件隔离组id|**Yes**|


#Response Elements
|Parameter name|Type|Description|Required|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|GroupId|string|硬件隔离组id|**Yes**|

#Request Example
```
https://api.ucloud.cn/?Action=DeleteIsolationGroup
&Region=cn-zj
&GroupId=GPrSAFjo
&ProjectId=USWvjZDj
```
#Response Example
```
{
    "GroupId": "FZBkhBxb",
    "RetCode": 0,
    "Action": "DeleteIsolationGroupResponse"
}
```

{{indexmenu_n>1000}}