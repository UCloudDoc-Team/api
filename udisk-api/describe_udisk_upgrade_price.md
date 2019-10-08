# 获取云硬盘升级价格-DescribeUDiskUpgradePrice

获取UDisk升级价格信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|Size|int|购买UDisk大小,单位:GB,范围[1~2000], 权限位控制可达8T,若需要请申请开通相关权限。|**Yes**|
|SourceId|string|升级目标UDisk ID|**Yes**|
|UDataArkMode|string|是否打开数据方舟, 打开"Yes",关闭"No", 默认关闭|No|
|DiskType|string|磁盘类型，SSDDataDisk:ssd数据盘,DataDisk:普通数据盘,SystemDisk:普通系统盘,SSDSystemDisk:ssd系统盘。默认为DataDisk|No|
|MachineType|string|云主机机型（V2.0），枚举值["N", "C", "G", "O", "OM"]。参考[[api:uhost-api:uhost_type|云主机机型说明]]。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|int|价格|No|
|OriginalPrice|int|用户折后价 (对应计费CustomPrice)|No|

# Request Example
```
https://api.ucloud.cn/udisk/?Action=DescribeUDiskUpgradePrice
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=1   
&SourceId=bsm-xxx
&UDataArkMode =Yes
&DiskType = DataDisk
&MachineType=bSHaETUa
```

# Response Example
```
{
    "Action": "DescribeUDiskUpgradePriceResponse", 
    "Price": 222, 
    "RetCode": 0, 
    "CustomPrice": 7
}
```

