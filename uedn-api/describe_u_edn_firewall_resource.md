# 防火墙绑定的资源列表-DescribeUEdnFirewallResource

防火墙绑定的资源列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FirewallId|string|防火墙Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ResourceSet|array|资源列表，详情参见ResourceInfo|**Yes**|
|TotalCount|int|资源总数|**Yes**|

## ResourceInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源Id|**Yes**|
|PublicIpList|array|节点公网Ip列表|**Yes**|
|Name|string|节点名称|**Yes**|
|State|int|节点状态，1部署中，2待启动，3启动中，4运行中，5正在停止，6已停止，7正在更新，8正在重启，9正在删除， 10已经删除,11异常|**Yes**|
|Remark|string|节点备注|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUEdnFirewallResource
&ProjectId=hIanQXfX
&FirewallId=MXScqFUD
```

# Response Example
```
{
    "Action": "DescribeUEdnFirewallResourceResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "ResourceSet": [
        {
            "ResourceId": "ITVxcmJL", 
            "State": 2, 
            "PublicIpList": [
                "HYXAllcI"
            ], 
            "Name": "tOajpETB", 
            "Remark": "FlXEQrwK"
        }
    ]
}
```

