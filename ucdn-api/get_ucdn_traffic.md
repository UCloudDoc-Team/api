# 获取流量信息-GetUcdnTraffic

获取流量信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TrafficSet|array|用户不同区域的流量信息, 具体结构参见TrafficSet部分|No|

## TrafficSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Areacode|string|购买流量的区域 ，cn代表国内 ，abroad代表海外。|No|
|TrafficTotal|float|areacode区域内总共购买的流量，单位GB|No|
|TrafficLeft|float|areacode区域内总共剩余流量，单位GB|No|
|TrafficUsed|float|areacode区域内总共使用流量，单位GB|No|

# Request Example
```
http://api.ucloud.cn/?Action=GetUcdnTraffic
&ProjectId=xxxxx
```

# Response Example
```
{
    "Action": "GetUcdnTrafficResponse", 
    "RetCode": 0, 
    "TrafficSet": [
        {
            "Areacode": "cn", 
            "TrafficTotal": 120, 
            "TrafficLeft": 100.1, 
            "TrafficUsed": 19.9
        }, 
        {
            "Areacode": "abroad", 
            "TrafficTotal": 120, 
            "TrafficLeft": 100.1, 
            "TrafficUsed": 19.9
        }
    ]
}
```

