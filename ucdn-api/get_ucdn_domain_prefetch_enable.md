# 获取域名预取开启状态-GetUcdnDomainPrefetchEnable

获取域名预取开启状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DomainId|string|域名ID，创建加速域名时生成。|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Enable|int|0表示该域名未开启预取，1表示该域名已开启预取|No|

# Request Example
```
http://api.ucloud.cn/?Action=GetUcdnDomainPrefetchEnable
&DomainId=ucdn-0331qd
```

# Response Example
```
{
    "Action": "GetUcdnDomainPrefetchEnableResponse", 
    "Enable": 0, 
    "RetCode": 0
}
```

