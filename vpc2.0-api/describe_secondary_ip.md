# 查询SecondaryIp-DescribeSecondaryIp

查询SecondaryIp（uk8s使用）

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SubnetId|string|子网Id|**Yes**|
|VPCId|string|VPCId|**Yes**|
|Ip|string|Ip|No|
|Mac|string|Mac|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array||No|

## IpInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Ip|string||No|
|Mask|string||No|
|Gateway|string||No|
|Mac|string||No|
|SubnetId|string||No|
|VPCId|string||No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeSecondaryIp
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=AoNgCvkX
&SubnetId=QfAOEXSt
&VPCId=jynlDzxI
&VPCId=gBCuTpQD
&Ip=OgMnUuly
&Mac=ZklzXnCK
```

# Response Example
```
{
    "Action": "DescribeSecondaryIpResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "VPCId": "DCeltDBF", 
            "Ip": "pzFfyUxt", 
            "Mask": "odqYlFTt", 
            "Mac": "saGJPQnC", 
            "SubnetId": "QGHAqxdN", 
            "Gateway": "THcrBgtL"
        }, 
        {
            "VPCId": "RjIGnCAB", 
            "Ip": "EAmSwUhq", 
            "Mask": "NIJJogNw", 
            "Mac": "TfrndLLZ", 
            "SubnetId": "RlQuDqll", 
            "Gateway": "ikjbDLGS"
        }, 
        {
            "VPCId": "odrmxTaN", 
            "Ip": "iiimiQCX", 
            "Mask": "UwQXlcpQ", 
            "Mac": "VdJDfgBW", 
            "SubnetId": "QDqLaStd", 
            "Gateway": "xjLsRaUU"
        }
    ]
}
```

