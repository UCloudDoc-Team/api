# 修改VPC地址空间-UpdateVPCNetwork

修改VPC地址空间，只支持删除地址空间

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|VPCId|string|VPC的ID|**Yes**|
|Network.n|string|更新的全量网段|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|错误信息|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateVPCNetwork
&Region=JEUZcbiD
&ProjectId=TdiFHZwY
&VPCId=wqKTIuky
&Network.n=MkgrMnxc
```

# Response Example
```
{
    "Action": "UpdateVPCNetworkResponse", 
    "Message": "KLzphjbP", 
    "RetCode": 0
}
```

