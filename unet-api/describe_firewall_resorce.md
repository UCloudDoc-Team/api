# 获取防火墙绑定资源-DescribeFirewallResource

获取防火墙组所绑定资源的外网IP

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|FWId|string|防火墙ID|**Yes**|
|Limit|int|返回数据长度，默认为20，最大10000000|No|
|Offset|int|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ResourceSet|array|资源列表，见 ResourceSet|No|
|TotalCount|int|绑定资源总数|No|

## ResourceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|int|可用区|No|
|Name|string|名称|No|
|PrivateIP|string|内网IP|No|
|Remark|string|备注|No|
|ResourceID|string|绑定该防火墙的资源id|No|
|ResourceType|string|绑定防火墙组的资源类型。"unatgw"，NAT网关； "uhost"，云主机； "upm"，物理云主机； "hadoophost"，hadoop节点； "fortresshost"，堡垒机； "udhost"，私有专区主机；"udockhost"，容器；"dbaudit"，数据库审计.|No|
|Status|int|状态|No|
|Tag|string|业务组|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeFirewallResource
&ProjectId=org-xxx
&Region=xxx
&FWId=fw-xxx
&Limit=20
&Offset=0
```

# Response Example
```
{
    "Action": "DescribeFirewallResourceResponse", 
    "TotalCount": 6, 
    "RetCode": 0, 
    "ResourceSet": [
        {
            "Status": 1, 
            "Remark": "", 
            "Name": "hc_host", 
            "Zone": 8200, 
            "ResourceType": "uhost", 
            "ResourceID": "uhost-XXXXXX", 
            "PrivateIP": "10.23.XX.XX", 
            "Tag": "Default"
        }
    ]
}
```

