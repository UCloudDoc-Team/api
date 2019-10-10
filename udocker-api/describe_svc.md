# 查询SVC信息-DescribeSVC

查询SVC信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SvcName|string|服务名|No|
|ClusterId|string|集群ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SvcSet|array|服务信息|No|

## SvcSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SvcName|string|服务名|**Yes**|
|ClusterId|string|集群ID|**Yes**|
|ProxyCount|int|代理数目|**Yes**|
|PodCount|int|Pod数目|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeSVC
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&SvcName=tttt
&ClusterId=cluster-xxx
```

# Response Example
```
{
    "Action": "DescribeSVCResponse", 
    "SvcSet": [
        {
            "Status": "running", 
            "PodCount": 3, 
            "ClusterId": "cluster-xxx", 
            "PortMap": {
                "80": "80"
            }, 
            "SvcName": "tttt", 
            "ProxyCount": 1
        }
    ], 
    "RetCode": 0
}
```

