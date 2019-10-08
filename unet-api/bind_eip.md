# 绑定弹性IP-BindEIP

将尚未使用的弹性IP绑定到指定的资源

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写|No|
|EIPId|string|弹性IP的资源Id|**Yes**|
|ResourceType|string|弹性IP请求绑定的资源类型, 枚举值为: uhost: 云主机; ulb, 负载均衡器 upm: 物理机; hadoophost: 大数据集群;fortresshost：堡垒机；udockhost：容器；udhost：私有专区主机；natgw：natgw；udb：udb；vpngw：ipsec vpn；ucdr：云灾备；dbaudit：数据库审计；|**Yes**|
|ResourceId|string|弹性IP请求绑定的资源ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BindEIP
&Region=cn-bj2
&EIPId=eip-XXXX
&ResourceType=uhost
&ResourceId=uhost-XXXXX
```

# Response Example
```
{
    "Action": "BindEIPResponse", 
    "Request_uuid": "1b52baa6-01ea-4cba-a6f9-XXXXXXXX", 
    "RetCode": 0
}
```

