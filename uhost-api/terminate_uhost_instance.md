#删除云主机-TerminateUHostInstance

删除指定数据中心的UHost实例。
```
非试用的过期资源不可删除； 关机状态下才能执行删除操作
```

#Request Parameters
|Parameter name|Type|Description|Required|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UHostId|string|UHost资源Id 参见 [DescribeUHostInstance](describe_uhost_instance.html)|**Yes**|
|Destroy|int|是否直接删除，0表示按照原来的逻辑（有回收站权限，则进入回收站），1表示直接删除|No|


#Response Elements
|Parameter name|Type|Description|Required|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|InRecycle|string|放入回收站:"Yes", 彻底删除：“No”|**Yes**|
|UHostId|string|UHost 实例 Id|No|

#Request Example
```
https://api.ucloud.cn/?Action=TerminateUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&UHostId=uhost-xxx
&ReleaseUDisk=true
```
#Response Example
```
{
    "RetCode": 0,
    "Action": "TerminateUHostInstanceResponse",
    "InRecycle": "No",
    "UHostId": "uhost-xxx"
}
```

{{indexmenu_n>1000}}