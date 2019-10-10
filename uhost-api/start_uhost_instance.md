# 启动主机-StartUHostInstance

启动处于关闭状态的UHost实例，需要指定数据中心及UHostID两个参数的值。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UHostId|string|UHost实例ID 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)|**Yes**|
|DiskPassword|string|加密盘密码|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UhostId|string|UHost实例ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=StartUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-qs20fr
```

# Response Example
```
{
    "Action": "StartUHostInstanceResponse", 
    "UHostId": "uhost-qs20fr", 
    "RetCode": 0
}
```

