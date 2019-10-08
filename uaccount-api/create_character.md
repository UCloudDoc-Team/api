# 创建角色-CreateCharacter

创建角色

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CharacterName|string|角色名称，不得与现有角色重名|**Yes**|
|CharacterDescription|string|角色描述|No|
|Add.n|string|角色对产品的权限(增)|No|
|Del.n|string|角色对产品的权限(删)|No|
|Mod.n|string|角色对产品的权限(改)|No|
|Get.n|string|角色对产品的权限(查)|No|

```
产品列表：云主机 UHOST、物理主机 UPHOST、托管云 UHYBRID、基础网络 UNET、负载均衡 ULB、云数据库 UDB、SSD云硬盘 UDISK、云内存存储 UMEM、对象存储 UFILE、分布式数据处理 UDDP、托管HADOOP集群 UHADOOP、云分发 UCDN、云点播 UVIDEO、基础安全防护 USEC、云数据仓库 UDW、分布式消息系统 UKAFKA、私有专区资源池 UDSET、AI在线服务 UAI、AI训练服务 UAI-TRAINING、云直播 ULIVE、容器服务 UDOCKER、公共镜像库 UHUB、WEB应用防护 UWAF、分布式数据库 UDDB、数据库审计 DBAUDIT、主机入侵检测 UHIDS、容器云 UK8S、密钥管理服务 UKMS、全球动态加速线路 PATHX、Elasticsearch服务 UES
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|CharacterId|string|角色ID|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateCharacter
&CharacterName=PkUHnfTq
&CharacterDescription=sOLKZcSH
&Add.n=OKlGsPhP
&Del.n=cZzFveLT
&Mod.n=GrixHXoU
&Get.n=nAKRweHk
```

# Response Example
```
{
    "Action": "CreateCharacterResponse", 
    "CharacterId": "WDmuiLnc", 
    "RetCode": 0
}
```

