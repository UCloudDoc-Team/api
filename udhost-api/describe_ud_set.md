# 查询资源池列表-DescribeUDSet

查询资源池列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|HostIds.n|string|资源池的短ID, 如果为空, 则返回当前Region所有资源池的配置信息，否则返回指定资源池的配置信息|No|
|Tag|string|要查询的业务组名称|No|
|Offset|int|数据偏移量, 默认为0|No|
|Limit|int|返回数据长度, 默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的总数|No|
|UDSet|array|获取的私有专区资源池列表|No|

## UDSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|资源池所在可用区|No|
|HostId|string|资源池的短ID|No|
|Tag|string|业务组名称|No|
|Remark|string|备注|No|
|Name|string|实例名称|No|
|SN|string|资源池的SN号|No|
|CreateTime|int|创建时间|No|
|HostIp|string|宿主机ip|No|
|UHostCount|int|主机数量|No|
|ChargeType|string|Year, Month|No|
|ExpireTime|int|到期时间|No|
|AutoRenew|string|是否自动续费，Yes，No|No|
|CPU|int|虚拟CPU核数, 单位:个|No|
|Memory|int|内存大小, 单位:MB|No|
|DiskSpace|int|数据盘大小, 单位: GB|No|
|UsedCPU|int|虚拟CPU核数, 单位:个|No|
|UsedMem|int|内存大小, 单位:MB|No|
|UsedDisk|int|数据盘大小, 单位: GB|No|

# Request Example
```
https://api.ucloud.cn?Action=DescribeUDSet
&Region=byeHKJgz
&HostIds.n=SFWoBpLC
&Tag=ZsdzeJXh
&Offset=4
&Limit=7
&ProjectId=seTvBjnI
```

# Response Example
```
{
    "Action": "DescribeUDSetResponse", 
    "TotalCount": 1, 
    "UDSet": [
        {
            "Remark": "", 
            "HostId": "udset-xxxx", 
            "UsedCPU": 0, 
            "Name": "", 
            "Zone": "cn-bj2-04", 
            "DiskSpace": 4096, 
            "Memory": 131072, 
            "UsedMem": 0, 
            "CPU": 32, 
            "ExpireTime": 1544521080, 
            "AutoRenew": "True", 
            "Tag": "Default", 
            "UsedDisk": 0, 
            "SN": "SN10231231421", 
            "ChargeType": "Year", 
            "HostIp": "10.10.10.10", 
            "UHostCount": 0, 
            "CreateTime": 1544521079
        }
    ], 
    "RetCode": 0
}
```

