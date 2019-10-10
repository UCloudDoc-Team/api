# 获取物理机信息-DescribePHost

获取物理机详细信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|PHostId.n|string|PHost资源ID，若为空，则返回当前Region所有PHost。|No|
|Offset|int|数据偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的PHost总数|No|
|PHostSet|array|PHost资源列表，参见 PHostSet|No|

## PHostSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|可用区，参见 [可用区列表](../summary/regionlist.html)|No|
|PHostId|string|PHost资源ID|No|
|SN|string|物理机序列号|No|
|PMStatus|string|物理云主机状态。枚举值：<br> > 初始化:Initializing; <br> > 启动中：Starting； <br> > 运行中：Running；<br> > 关机中：Stopping； <br> > 安装失败：InstallFailed； <br> > 重启中：Rebooting；<br> > 关机：Stopped；|No|
|Name|string|物理机名称|No|
|Remark|string|物理机备注|No|
|Tag|string|业务组|No|
|ImageName|string|镜像名称|No|
|OSname|string|操作系统名称|No|
|CreateTime|int|创建时间|No|
|ExpireTime|int|到期时间|No|
|ChargeType|string|计费模式，枚举值为： Year，按年付费； Month，按月付费； Dynamic，按需付费（需开启权限）； Trial，试用（需开启权限）默认为月付|No|
|PowerState|string|电源状态，on 或 off|No|
|PHostType|string|物理机类型，参见DescribePHostMachineType返回值|No|
|Memory|int|内存大小，单位：MB|No|
|CPUSet|object|CPU信息，见 PHostCPUSet|No|
|DiskSet|array|磁盘信息，见 PHostDiskSet|No|
|IPSet|array|IP信息，见 PHostIPSet|No|
|Cluster|string|网络环境。枚举值：千兆：1G ，万兆：10G|No|
|AutoRenew|string|自动续费|No|
|IsSupportKVM|string|是否支持紧急登录|No|
|OSType|string|操作系统类型|No|
|Components|string|组件信息（暂不支持）|No|
|RaidSupported|string|是否支持Raid。枚举值：Yes：支持；No：不支持。|No|

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

## PHostIPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|OperatorName|string| 国际: Internation， BGP: BGP， 内网: Private |No|
|IPId|string|IP资源ID(内网IP无资源ID)（待废弃）|No|
|IPAddr|string|IP地址，|No|
|MACAddr|string|MAC地址|No|
|Bandwidth|int|IP对应带宽，单位Mb，内网IP不显示带宽信息|No|
|SubnetId|string|子网ID|No|
|VPCId|string|VPC ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribePHost
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&Offset=0
&Limit=20
&PHostId.0=upm-xxx
```

# Response Example
```
{
    "Action": "DescribePHostResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "PHostSet": [
        {
            "Remark": "", 
            "Tag": "Default", 
            "PowerState": "On", 
            "Name": "apyapy", 
            "Zone": "cn-bj2-04", 
            "CPUSet": {
                "Count": 2, 
                "Model": "Intel E5-2630 v3", 
                "CoreCount": 32, 
                "Frequence": 2.4000000953674316
            }, 
            "ImageName": "CentOS 6.7 64Bit", 
            "OSname": "CentOS 6.7 64Bit", 
            "ExpireTime": 1530374400, 
            "AutoRenew": "On", 
            "PHostId": "upm-xxx", 
            "PMStatus": "Running", 
            "SN": "817336542", 
            "ChargeType": "Month", 
            "Memory": 65536, 
            "OSType": "CentOS", 
            "IPSet": [
                {
                    "IPId": "eip-xxx", 
                    "Bandwidth": 2, 
                    "IPAddr": "106.75.xxx.xxx", 
                    "OperatorName": "Bgp"
                }, 
                {
                    "SubnetId": "subnet-xxx", 
                    "MACAddr": "xxx", 
                    "IPAddr": "10.10.xxx.xxx", 
                    "OperatorName": "Private", 
                    "VPCId": "uvnet-xxx"
                }
            ], 
            "IsSupportKVM": "Yes", 
            "CreateTime": 1529905686, 
            "DiskSet": [
                {
                    "IOCap": 1000, 
                    "Type": "SATA", 
                    "Raid": "Raid1", 
                    "Name": "sys", 
                    "Space": 1000
                }, 
                {
                    "IOCap": 1000, 
                    "Type": "SAS", 
                    "Raid": "Raid10", 
                    "Name": "data", 
                    "Space": 1800
                }
            ], 
            "PHostType": "DB-2"
        }
    ]
}
```

