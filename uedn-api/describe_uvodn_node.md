# 获取节点列表-DescribeUvodnNode

获取节点列表 2.0

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|IdcId.n|string|Idc机房id。默认全部机房|No|
|NodeId.n|string|节点id，创建节点时生成的id。默认全部节点|No|
|Offset|int|数据偏移量，默认0，非负整数|No|
|Limit|int|返回数据长度， 默认20，非负整数|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的节点总数|No|
|NodeList|array|节点列表|No|

## NodeInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NodeName|string|节点名称|No|
|NodeId|string|节点ID|No|
|CoreNum|int|Cpu核数|No|
|MemSize|int|节点内存大小，单位GB|No|
|SysDiskSize|int|系统盘大小， 单位GB|No|
|DiskSize|int|数据盘大小， 单位GB|No|
|State|int|节点状态，1部署中，2待启动，3启动中，4运行中，5正在停止，6已停止，7正在更新，8正在重启，9正在删除， 10已经删除,11异常|No|
|NetLimit|int|节点带宽限制， 单位Mbs|No|
|IdcId|string|机房ID|No|
|OcName|string|机房名称|No|
|Province|string|省份|No|
|City|string|城市|No|
|Type|int|运营商类型： 0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通|No|
|ChargeType|int|付费类型：1按时, 2按月,3按年|No|
|CreateTime|int|创建时间|No|
|ExpiredTime|int|过期时间|No|
|ImageName|string|镜像名称|No|
|NodeIpList|array|外网ip集合|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUvodnNode
&ProjectId=org-xxx
&IdcId.0=uedn-idc-xxx
&NodeId.0=uedn-node-xxx
```

# Response Example
```
{
    "Action": "DescribeUvodnNodeResponse", 
    "TotalCount": 1, 
    "NodeList": [
        {
            "SysDiskSize": 20, 
            "Province": "北京市", 
            "ImageName": "CentOS 7.2 64位", 
            "OcName": "北京市-北京市-电信", 
            "NodeName": "jht-test-01", 
            "City": "北京市", 
            "CoreNum": 1, 
            "NodeIpList": [
                {
                    "Ip": "106.9.5.14", 
                    "Isp": " "
                }
            ], 
            "InnerIps": [
                "10.10.9.2"
            ], 
            "NodeId": "uedn-node-xxx", 
            "ImageId": "uedn-image-xxx", 
            "State": 4, 
            "ExpiredTime": 1579850247, 
            "DiskSize": 20, 
            "ChargeType": 2, 
            "MemSize": 2, 
            "IdcId": "uedn-idc-xxx", 
            "NetLimit": 2, 
            "Type": 1, 
            "CreateTime": 1577258247
        }
    ], 
    "RetCode": 0
}
```

