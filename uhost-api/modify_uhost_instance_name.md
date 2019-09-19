#修改主机名-ModifyUHostInstanceName

修改指定UHost实例名称，需要给出数据中心，UHostId，及新的实例名称。

#Request Parameters
|Parameter name|Type|Description|Required|
|Region|string|地域，参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区，参见 [可用区列表](../summary/regionlist.html)|No|
|UHostId|string|UHost实例ID 参见 [DescribeUHostInstance](describe_uhost_instance.html)|**Yes**|
|Name|string|UHost实例名称|No|
|ProjectId|string|项目编号（子帐号用） 请参考GetProjectList接口|No|


#Response Elements
|Parameter name|Type|Description|Required|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UhostId|string|UHost实例ID|No|

#Request Example
```
http(s)://api.ucloud.cn/?Action=ModifyUHostInstanceName
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-qs20fr
&Name=Test
```
#Response Example
```
{
    "Action": "ModifyUHostInstanceNameResponse",
    "UHostId": "uhost-qs20fr",
    "RetCode": 0
}
```

{{indexmenu_n>1000}}