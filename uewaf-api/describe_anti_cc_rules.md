# CC防御规则列表-DescribeAntiCCRules

CC防御规则列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Domain|string|要查询防护规则的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Res|object|CC规则，参考AntiCcRes|No|

## AntiCcRes
|Parameter name|Type|Description|Required|
|---|---|---|---|
|State|string|指定域名的CC防护状态|**Yes**|
|Mode|string|指定域名的CC防护模式|**Yes**|
|Max|string|CC规则最大容量|**Yes**|
|Rules|array|CC规则列表，参考AntiCcRule|**Yes**|

## AntiCcRule
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Id|int|规则ID|**Yes**|
|Uri|string|URI|**Yes**|
|Mode|string|模式|**Yes**|
|Duration|int|统计时长. 单位:秒|**Yes**|
|Reqs|int|请求次数|**Yes**|
|Action|string|执行动作|**Yes**|
|Validity|string|动作有效期,单位:分钟|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeAntiCCRules
&ProjectId=org-xxx
&Domain=www.test.com
```

# Response Example
```
{
    "Action": "DescribeAntiCCRulesResponse", 
    "Res": {
        "Rules": [
            {
                "Uri": "/index.html", 
                "Validity": 60, 
                "Reqs": 2, 
                "Action": "forbidden", 
                "Mode": "equal", 
                "Duration": 10, 
                "Id": 43804
            }, 
            {
                "Uri": "/index.html", 
                "Validity": 60, 
                "Reqs": 20, 
                "Action": "forbidden", 
                "Mode": "equal", 
                "Duration": 10, 
                "Id": 44451
            }
        ], 
        "Max": 30, 
        "State": "on", 
        "Mode": "normal"
    }, 
    "RetCode": 0
}
```

