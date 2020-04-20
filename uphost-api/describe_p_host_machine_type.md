# 获取物理云机型信息-DescribePHostMachineType

获取物理云机型的详细描述信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Type|string|具体机型。若不填写，则返回全部机型|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|MachineTypes|array|机型列表，模型：PHostMachineTypeSet|**Yes**|

## PHostMachineTypeSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Type|string|物理云主机机型别名，全网唯一。|**Yes**|
|Name|string|机型名|No|
|CPU|object|CPU信息|No|
|Memory|int|内存大小，单位GB|No|
|Disks|array|磁盘信息|No|
|Components|object|其他组件信息|No|
|Clusters|array|集群库存信息|No|
|RaidSupported|string|是否支持Raid。枚举值：支持：YES；不支持：NO|No|

## PHostCPUSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Model|string|CPU型号|No|
|Frequence|float|CPU主频|No|
|Count|int|CPU个数|No|
|CoreCount|int|CPU核数|No|

## PHostDiskSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Space|int|单盘大小，单位GB|No|
|Count|int|磁盘数量|No|
|Type|string|磁盘属性|No|
|Name|string|磁盘名称，sys/data|No|
|IOCap|int|磁盘IO性能，单位MB/s（待废弃）|No|

## PHostComponentSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|组件名称|No|
|Count|string|组件数量|No|

## PHostClusterSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|集群名。枚举值：千兆网络集群：1G；万兆网络集群：10G|No|
|StockStatus|string|库存状态。枚举值：有库存：Available；无库存：SoldOut|No|

# Request Example
```
https://api.ucloud.cn/?Action=DecribePHostMachineType
&Region=cn-bj2
&Zone=cn-bj2-02
```

# Response Example
```
{
    "Action": "DescribePHostMachineTypeResponse", 
    "MachineTypes": [
        {
            "Disks": [
                {
                    "Count": 2, 
                    "IOCap": 1000, 
                    "Type": "SATA", 
                    "Name": "sys", 
                    "Space": 1000
                }, 
                {
                    "Count": 6, 
                    "IOCap": 1000, 
                    "Type": "SAS", 
                    "Name": "data", 
                    "Space": 600
                }
            ], 
            "RaidSupported": "YES", 
            "Components": {
                "Count": 0, 
                "Name": ""
            }, 
            "Memory": 65536, 
            "Clusters": [
                {
                    "StockStatus": "SoldOut", 
                    "Name": "10G"
                }
            ], 
            "Type": "DB-2", 
            "CPU": {
                "Count": 2, 
                "Model": "Intel E5-2630 v3", 
                "CoreCount": 32, 
                "Frequence": "2.40"
            }
        }
    ], 
    "RetCode": 0
}
```

