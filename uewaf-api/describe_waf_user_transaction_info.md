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
|ResourceId|string|资源ID|**Yes**|
|Editon|string|版本类型|**Yes**|
|ExpireTime|string|服务到期时间|**Yes**|
|ChargeType|string|付费类型|**Yes**|
|Price|float|购买价格，单位：元，精确到分|**Yes**|
|TransactionId|int|资源的唯一索引|**Yes**|
|TransactionNo|string|资源订单号|**Yes**|
|HasWaf|bool|是否购买了WAF|**Yes**|
|Expired|string|是否已过期，有此字段即为已过期|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafUserTransactionInfo
&ProjectId=XuimDpSE
```

# Response Example
```
{
    "Action": "DescribeWafUserTransactionInfoResponse", 
    "TransactionInfo": {
        "ResourceId": "usecure_uewaf-y2g35t", 
        "Price": 66666, 
        "ExpireTime": "2016-12-29 20:18:59", 
        "ChargeType": "Month", 
        "Editon": "Enterprise", 
        "TransactionId": 32, 
        "Quantity": 2
    }, 
    "RetCode": 0
}
```

