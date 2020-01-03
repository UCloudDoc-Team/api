# 获取节点调整差价-GetUEdnUpgradePrice

获取节点调整差价

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NodeId|string|节点ID|**Yes**|
|CpuCore|int|cpu核心数|No|
|MemSize|int|内存大小，单位GB|No|
|SysDiskSize|int|系统盘大小，单位GB|No|
|DiskSize|int|数据盘大小，单位GB|No|
|NetLimit|int|节点带宽限制，单位Mbs|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|int|规格调整差价|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUEdnUpgradePrice
&ProjectId=WpNYPaff
&NodeId=bDOTSYGZ
&CpuCore=5
&MemSize=6
&SysDiskSize=3
&DiskSize=9
&NetLimit=3
```

# Response Example
```
{
    "Action": "GetUEdnUpgradePriceResponse", 
    "Price": 5, 
    "RetCode": 0
}
```

