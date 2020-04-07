# 获取用户购买详细信息-DescribeWafUserTransactionInfo

获取用户购买的详细信息，包括资源ID，版本类型，过期时间，付费方式，购买价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TransactionInfo|array|用户购买服务的详细信息，参考TransactionInfo|**Yes**|

## TransactionInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源ID|No|
|Editon|string|版本类型|No|
|ExpireTime|string|服务到期时间|No|
|ChargeType|string|付费类型|No|
|Price|float|购买价格，单位：元，精确到分|No|
|TransactionId|int|资源的唯一索引|No|
|TransactionNo|string|资源订单号|No|
|HasWaf|bool|是否购买了WAF|No|
|Expired|string|是否已过期，有此字段即为已过期|No|
|WorkRegions|string|部署区域|No|
|Serving|string|服务是否生效中|No|
|LogStorage|int|是否开启日志扩展包|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafUserTransactionInfo
&ProjectId=org-xxx
```

# Response Example
```
{
    "Action": "DescribeWafUserTransactionInfoResponse", 
    "TransactionInfo": {
        "TransactionNo": "20170410050160160645159", 
        "Serving": "Y", 
        "ResourceId": "usecure_uewaf-lbjszn", 
        "LogStorage": 0, 
        "WorkRegions": "cn-gd,cn-sh,hk,cn-bj,tw-tp,us-ca,kr-seoul,jpn-tky", 
        "WorkZone": "mainland", 
        "ExpireTime": "2020-06-03 00:00:00", 
        "HasWaf": true, 
        "ChargeType": "Month", 
        "Editon": "Professional", 
        "TransactionId": 31, 
        "Expired": "", 
        "CreateTime": "2017-04-10 13:30:05"
    }, 
    "RetCode": 0
}
```

