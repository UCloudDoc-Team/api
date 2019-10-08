# 获取SQL查询结果-GetSQLQueryData

获取用户指定的SQL查询运行后的结果数据

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|QueryId|string|SQL查询ID|**Yes**|
|Limit|int|获取的数据记录数上限|**Yes**|
|Marker|string|数据记录偏移，从开始位置获取的时候不需要填写。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|QueryId|string|SQL查询ID|No|
|Marker|string|下一批数据记录的偏移位置|No|
|Header|array|结果数据的字段列表，类型是字符串的集合|No|
|Rows|array|结果数据集合， 数组中每一项代表1条记录。|No|
|QueryType|string|查询类型，有SELECT， CREATE_TABLE等多种SQL类型|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetSQLQueryData
&Region=pre
&QueryId=20180913_115922_00001_22dwf
&Limit=5
&Marker=347


&ProjectId=RZKDQone
```

# Response Example
```
{
    "Rows": [
        [
            "1", 
            "ARGENTINA", 
            "1", 
            "al foxes promise slyly according to the regular accounts. bold requests alon"
        ], 
        [
            "2", 
            "BRAZIL", 
            "1", 
            "y alongside of the pending deposits. carefully special packages are about the ironic forges. slyly special "
        ], 
        [
            "3", 
            "CANADA", 
            "1", 
            "eas hang ironic, silent packages. slyly regular packages are furiously over the tithes. fluffily bold"
        ], 
        [
            "4", 
            "EGYPT", 
            "4", 
            "y above the carefully unusual theodolites. final dugouts are quickly across the furiously regular d"
        ], 
        [
            "5", 
            "ETHIOPIA", 
            "0", 
            "ven packages wake quickly. regu"
        ], 
        [
            "6", 
            "FRANCE", 
            "3", 
            "refully final requests. regular, ironi"
        ], 
        [
            "7", 
            "GERMANY", 
            "3", 
            "l platelets. regular accounts x-ray: unusual, regular acco"
        ], 
        [
            "8", 
            "INDIA", 
            "2", 
            "ss excuses cajole slyly across the packages. deposits print aroun"
        ], 
        [
            "9", 
            "INDONESIA", 
            "2", 
            " slyly express asymptotes. regular deposits haggle slyly. carefully ironic hockey players sleep blithely. carefull"
        ], 
        [
            "10", 
            "IRAN", 
            "4", 
            "efully alongside of the slyly final dependencies. "
        ]
    ], 
    "RetCode": 0, 
    "Header": [
        "n_nationkey", 
        "n_name", 
        "n_regionkey", 
        "n_comment"
    ], 
    "Request": "16acec76-84f1-4504-bbbc-f7b49d06e710", 
    "Marker": "945", 
    "QueryId": "20180913_115922_00001_22dwf", 
    "Action": "GetSQLQueryDataResponse", 
    "QueryType": "MGTOLrwa"
}
```

