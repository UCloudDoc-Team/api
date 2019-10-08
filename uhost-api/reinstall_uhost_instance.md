# 重装系统-ReinstallUHostInstance

重新安装指定UHost实例的操作系统

```
1.请确认在重新安装之前，该实例已被关闭； 2.请确认该实例未挂载UDisk； 3.将原系统重装为不同类型的系统时(Linux-&gt;Windows)，不可选择保留数据盘； 4.重装不同版本的系统时(CentOS6-&gt;CentOS7)，若选择保留数据盘，请注意数据盘的文件系统格式； 5.若主机CPU低于2核，不可重装为Windows系统。
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UHostId|string|UHost实例资源ID 参见 [DescribeUHostInstance](describe_uhost_instance.html)|**Yes**|
|Password|string|如果创建UHost实例时LoginMode为Password，则必须填写，如果LoginMode为KeyPair，不需要填写 （密码格式使用BASE64编码；LoginMode不可变更）|No|
|ImageId|string|镜像Id，默认使用原镜像 参见 [DescribeImage](describe_image.html)|No|
|ReserveDisk|string|是否保留数据盘，保留：Yes，不报留：No， 默认：Yes|No|
|ResourceType|int|云灾备指明191|No|
|DNSServers.n|string|针对非私有子网主机，可自定义DNS。n可为0-2|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UhostId|string|UHost实例资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=ReinstallUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-qs20fr
&Password=UCloud123
```

# Response Example
```
{
    "Action": "ReinstallUHostInstanceResponse", 
    "UHostId": "uhost-qs20fr", 
    "RetCode": 0
}
```

