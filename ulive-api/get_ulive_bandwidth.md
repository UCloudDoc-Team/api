# 获取直播加速带宽流量-GetUliveBandwidth

获取直播加速带宽流量

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Type|int|带宽查询粒度，0：5分钟；1：1小时；2：1天；	 3：1分钟|**Yes**|
|DomainId.n|string|域名ID，创建域名时生成的ID，不传则获取所有|No|
|Domain.n|string|域名,没有则获取域名id下的所有域名带宽和|No|
|BeginTime|int|查询流量的起始时间，格式：时间戳|No|
|EndTime|int|查询流量的结束时间，格式：时间戳|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BandwidthSet|array|带宽流量实例表。|No|
|Traffic|float|从起始时间到结束时间内所使用的总流量，单位GB|No|
|MaxBandwidth|float|从起始时间到结束时间内带宽峰值|No|

## BandwidthSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|带宽获取的时间点。格式：时间戳|No|
|Value|float|带宽数值|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUliveBandwidth
&DomainId.n=hZZqcYcV
&Domain.n=wtDaSfIh
&Type=8
&BeginTime=4
&EndTime=5
```

# Response Example
```
{
    "Action": "GetUliveBandwidthResponse", 
    "BandwidthSet": [
        {
            "Value": 5.18889, 
            "Time": 8
        }, 
        {
            "Value": 9.13735, 
            "Time": 4
        }, 
        {
            "Value": 1.22747, 
            "Time": 6
        }
    ], 
    "Traffic": 7.66794, 
    "RetCode": 0, 
    "MaxBandwidth": 4.67111
}
```

