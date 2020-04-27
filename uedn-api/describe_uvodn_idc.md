# 获取IDC机房列表-DescribeUvodnIDC

UEDN

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Cpu|int|节点cpu核数|**Yes**|
|Memory|int|节点内存大小， 单位GB|**Yes**|
|IdcId.n|string|Idc机房id。默认全部机房|No|
|Type|int|0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通|No|
|ProductType|string|产品类型：normal（通用型），hf（高主频型）|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的镜像|No|
|IdcList|array|获取的机房信息，具体参考下面IdcInfo|No|

## IdcInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IdcId|string|机房ID|No|
|Name|string|机房名称|No|
|Isp|string|运营商|No|
|Province|string|省份|No|
|City|string|城市|No|
|Type|int|运营商类型：0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通|No|
|MaxNodeCnt|int|机房可创建节点最大数量|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUvodnIDC
&ProjectId=org-xxx
&IdcId.0=uedn-idc-xxx
&Cpu=2
&Memory=4
&Type=1
&ProductType=chHMcgdE
```

# Response Example
```
{
    "Action": "DescribeUvodnIDCResponse", 
    "TotalCount": 9, 
    "IdcList": [
        {
            "Province": "北京市", 
            "City": "北京市", 
            "Name": "北京市-北京市-电信", 
            "MaxNodeCnt": 2, 
            "Isp": "电信", 
            "IdcId": "uedn-idc-xxx", 
            "Type": 1
        }, 
        {
            "Province": "广东省", 
            "City": "深圳市", 
            "Name": "广东省-深圳市-电信", 
            "MaxNodeCnt": 2, 
            "Isp": "电信", 
            "IdcId": "uedn-idc-xxx", 
            "Type": 1
        }
    ], 
    "RetCode": 0
}
```

