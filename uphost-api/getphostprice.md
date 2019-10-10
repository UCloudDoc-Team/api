# 获取物理机价格-GetPHostPrice

获取物理机价格列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Count|int|购买数量，范围[1-5]|**Yes**|
|ChargeType|string|计费模式，枚举值为： Year/Month/Trial/Dynamic|**Yes**|
|Quantity|int|购买时长，1-10个月或1-10年|**Yes**|
|Type|string|默认为：DB(数据库型)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PriceSet|array|价格列表 见 PHostPriceSet|No|

## PHostPriceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|Year/Month/Trial/Dynamic|No|
|Price|float|价格, 单位:元, 保留小数点后两位有效数字|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetPHostPrice
&ProjectId=562
&Region=cn-bj2
&Zone=cn-bj2-04
&Count=1
&Type=DB
&ChargeType=Month
&Quantity=1
```

# Response Example
```
{
    "Action": "GetPHostPriceResponse", 
    "PriceSet": [
        {
            "Price": 4000, 
            "ChargeType": "Month"
        }
    ], 
    "RetCode": 0
}
```

