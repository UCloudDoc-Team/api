# 删除VPN隧道-DeleteVPNTunnel

删除VPN隧道

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|VPNTunnelId|string|VPN隧道的资源ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteVPNTunnel
&Region=cn-sh2
&ProjectId=org-XXXXXX
&VPNTunnelId=vpntunnel-XXXXX
```

# Response Example
```
{
    "Action": "DeleteVPNTunnelResponse", 
    "RetCode": 0
}
```

