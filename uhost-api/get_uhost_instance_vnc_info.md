# 获取VNC登录信息-GetUHostInstanceVncInfo

获取指定UHost实例的管理VNC配置详细信息。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UHostId|string|UHost实例ID 参见 [DescribeUHostInstance](./api/uhost-api/describe_uhost_instance)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UhostId|string|UHost实例ID|No|
|VncIP|string|Vnc登录IP|No|
|VncPort|int|Vnc登录端口|No|
|VncPassword|string|Vnc 登录密码|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUHostInstanceVncInfo
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-qs20fr
```

# Response Example
```
{
    "VncIP": "118.192.93.9", 
    "VncPassword": "Y33WrImq", 
    "RetCode": 0, 
    "UHostId": "uhost-qs20fr", 
    "Action": "GetUHostInstanceVncInfoResponse", 
    "VncPort": "1234"
}
```

