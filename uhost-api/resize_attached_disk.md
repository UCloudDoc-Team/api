# 修改挂载的磁盘大小-ResizeAttachedDisk

修改挂载的磁盘大小，包含系统盘和数据盘

```
1.修改配置前，请确认该实例已经被关闭。
2.修改磁盘空间大小后，请在启动后按照说明，进入操作系统进行操作。
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UHostId|string|UHost实例ID。 参见 [DescribeUHostInstance](describe_uhost_instance.html)。|**Yes**|
|DiskSpace|int|磁盘大小，单位GB，步长为10。取值范围需大于当前磁盘大小，最大值请参考[[api:uhost-api:disk_type|磁盘类型]]。|**Yes**|
|DiskId|string|磁盘ID。参见 [DescribeUHostInstance](describe_uhost_instance.html)返回值中的DiskSet。|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DiskId|string|改配成功的磁盘id|No|

# Request Example
```
https://api.ucloud.cn/?Action=ResizeAttachedDisk
&Region=cn-sh2
&Zone=cn-sh2-02
&UHostId=uhost-qfbc2i
&DiskId=bs-w5oyip
&DiskSpace=40
```

# Response Example
```
{
    "Action": "ResizeAttachedDiskResponse", 
    "RetCode": 0, 
    "DiskId": "bs-w5oyip"
}
```

