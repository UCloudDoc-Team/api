# 解绑弹性IP-UnBindEIP

将弹性IP从资源上解绑

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|EIPId|string|弹性IP的资源Id|**Yes**|
|ResourceType|string|弹性IP请求解绑的资源类型, 枚举值为: uhost: 云主机; ulb, 负载均衡器 upm: 物理机; hadoophost: 大数据集群;fortresshost：堡垒机；udockhost：容器；udhost：私有专区主机；natgw：NAT网关；udb：udb；vpngw：ipsec vpn；ucdr：云灾备；dbaudit：数据库审计；|**Yes**|
|ResourceId|string|弹性IP请求解绑的资源ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UnBindEIP
&Region=cn-bj2
&EIPId=eip-XXXXX
&ResourceType=uhost
&ResourceId=uhost-XXXXX
```

# Response Example
```
{
    "Action": "UnBindEIPResponse", 
    "Request_uuid": "75d21a69-95d5-4efd-b165-XXXXXXX", 
    "RetCode": 0
}
```

