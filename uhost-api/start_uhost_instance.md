#启动主机-StartUHostInstance

启动处于关闭状态的UHost实例，需要指定数据中心及UHostID两个参数的值

#Request Parameters
|Parameter name|Type|Description|Required|
|Region|string|地域，参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区，参见 [可用区列表](../summary/regionlist.html)|No|
|UHostId|string|UHost实例ID 参见 [DescribeUHostInstance](describe_uhost_instance.html)|**Yes**|
|ProjectId|string|项目编号（子帐号用） 请参考GetProjectList接口|No|
|DiskPassword|string|加密盘密码|No|


#Response Elements
|Parameter name|Type|Description|Required|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UhostId|string|UHost实例ID|No|

#Request Example
```
http(s)://api.ucloud.cn/?Action=StartUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-qs20fr
```
#Response Example
```
{
    "Action": "StartUHostInstanceResponse",
    "UHostId": "uhost-qs20fr",
    "RetCode": 0
}
```

{{indexmenu_n>4}}