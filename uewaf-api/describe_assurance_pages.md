# 获取防篡改页面列表-DescribeAssurancePages

获取防篡改页面列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Domain|string|要获取的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Res|object|防篡改信息，参考AssurancePages|No|

## AssurancePages
|Parameter name|Type|Description|Required|
|---|---|---|---|
|State|string|防篡改全局状态|**Yes**|
|TotalCount|int|防篡改配置总数|**Yes**|
|Limit|int|防篡改规则配额|**Yes**|
|Items|array|防篡改规则列表，参考AssuracePagesDetail|**Yes**|

## AssuracePagesDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ID|int|反篡改规则ID|**Yes**|
|URL|string|防篡改页面url|**Yes**|
|State|string|防护状态|**Yes**|
|Remark|string|备注信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeAssurancePages
&ProjectId=org-xxx
&Domain=www.test.com
```

# Response Example
```
{
    "Action": "DescribeAssurancePagesResponse", 
    "Res": {
        "TotalCount": 1, 
        "State": "off", 
        "Limit": 19, 
        "Items": [
            {
                "Url": "http://www.test.com/inedx.html", 
                "Remark": "q", 
                "Id": 368, 
                "State": "on"
            }
        ]
    }, 
    "RetCode": 0
}
```

