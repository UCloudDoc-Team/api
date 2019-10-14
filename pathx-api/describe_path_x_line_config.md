# 获取全球加速线路信息-DescribePathXLineConfig

获取全球加速线路信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|LineSet|array|UGAA线路列表|No|

## UGAALine
|Parameter name|Type|Description|Required|
|---|---|---|---|
|LineFrom|string|线路源|**Yes**|
|LineTo|string|线路目的|**Yes**|
|LineId|string|线路计费Id|No|
|LineFromName|string|线路源中文名称|**Yes**|
|LineToName|string|线路目的中文名称|**Yes**|
|LineDetail|array|子线路信息|No|

## LineDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|LineFrom|string|线路源|**Yes**|
|LineTo|string|线路目的|**Yes**|
|LineId|string|线路计费Id|No|
|LineFromName|string|线路源中文名称|**Yes**|
|LineToName|string|线路目的中文名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribePathXLineConfig
&ProjectId=org-xxxx
```

# Response Example
```
{
    "Action": "DescribePathXLineConfigResponse", 
    "LineSet": [
        {
            "LineFromName": "拉各斯", 
            "LineToName": "中国", 
            "LineFrom": "afr-nigeria", 
            "LineTo": "cn-bj2", 
            "LineId": "line_afr-nigeria_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "拉各斯", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "afr-nigeria", 
                    "LineId": "line_afr-nigeria_cn-bj2", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "拉各斯", 
            "LineToName": "法兰克福", 
            "LineFrom": "afr-nigeria", 
            "LineTo": "ge-fra", 
            "LineId": "line_afr-nigeria_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "拉各斯", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "afr-nigeria", 
                    "LineId": "line_afr-nigeria_ge-fra", 
                    "LineToName": "法兰克福"
                }
            ]
        }, 
        {
            "LineFromName": "圣保罗", 
            "LineToName": "洛杉矶", 
            "LineFrom": "bra-saopaulo", 
            "LineTo": "us-ca", 
            "LineId": "line_bra-saopaulo_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "圣保罗", 
                    "LineTo": "us-ca", 
                    "LineFrom": "bra-saopaulo", 
                    "LineId": "line_bra-saopaulo_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "中国", 
            "LineToName": "法兰克福", 
            "LineFrom": "cn-bj2", 
            "LineTo": "ge-fra", 
            "LineId": "line_cn-bj2_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "中国", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_ge-fra", 
                    "LineToName": "法兰克福"
                }
            ]
        }, 
        {
            "LineFromName": "中国", 
            "LineToName": "洛杉矶", 
            "LineFrom": "cn-bj2", 
            "LineTo": "us-ca", 
            "LineId": "line_cn-bj2_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "中国", 
                    "LineTo": "us-ca", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "中国", 
            "LineToName": "中国香港", 
            "LineFrom": "cn-gd", 
            "LineTo": "hk", 
            "LineId": "line_cn-gd_hk", 
            "LineDetail": [
                {
                    "LineFromName": "中国", 
                    "LineTo": "hk", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "法兰克福", 
            "LineFrom": "cn-gd", 
            "LineTo": "ge-fra", 
            "LineId": "line_cn-ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_ge-fra", 
                    "LineToName": "法兰克福"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_ge-fra", 
                    "LineToName": "法兰克福"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_ge-fra", 
                    "LineToName": "法兰克福"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "中国香港", 
            "LineFrom": "cn-gd", 
            "LineTo": "hk", 
            "LineId": "line_cn-hk", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "hk", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_hk", 
                    "LineToName": "中国香港"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "hk", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_hk", 
                    "LineToName": "中国香港"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "hk", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "洛杉矶", 
            "LineFrom": "cn-gd", 
            "LineTo": "us-ca", 
            "LineId": "line_cn-us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "us-ca", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_us-ca", 
                    "LineToName": "洛杉矶"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "us-ca", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_us-ca", 
                    "LineToName": "洛杉矶"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "us-ca", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "拉各斯", 
            "LineFrom": "cn-gd", 
            "LineTo": "afr-nigeria", 
            "LineId": "line_cn_afr-nigeria", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "afr-nigeria", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_afr-nigeria", 
                    "LineToName": "拉各斯"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "afr-nigeria", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_afr-nigeria", 
                    "LineToName": "拉各斯"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "afr-nigeria", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_afr-nigeria", 
                    "LineToName": "拉各斯"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "雅加达", 
            "LineFrom": "cn-gd", 
            "LineTo": "idn-jakarta", 
            "LineId": "line_cn_idn-jakarta", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_idn-jakarta", 
                    "LineToName": "雅加达"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_idn-jakarta", 
                    "LineToName": "雅加达"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_idn-jakarta", 
                    "LineToName": "雅加达"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "孟买", 
            "LineFrom": "cn-gd", 
            "LineTo": "ind-mumbai", 
            "LineId": "line_cn_ind-mumbai", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_ind-mumbai", 
                    "LineToName": "孟买"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_ind-mumbai", 
                    "LineToName": "孟买"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_ind-mumbai", 
                    "LineToName": "孟买"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "东京", 
            "LineFrom": "cn-gd", 
            "LineTo": "jpn-tky", 
            "LineId": "line_cn_jpn-tky", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_jpn-tky", 
                    "LineToName": "东京"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_jpn-tky", 
                    "LineToName": "东京"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_jpn-tky", 
                    "LineToName": "东京"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "莫斯科", 
            "LineFrom": "cn-gd", 
            "LineTo": "rus-mosc", 
            "LineId": "line_cn_rus-mosc", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "rus-mosc", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_rus-mosc", 
                    "LineToName": "莫斯科"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "rus-mosc", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_rus-mosc", 
                    "LineToName": "莫斯科"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "rus-mosc", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_rus-mosc", 
                    "LineToName": "莫斯科"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "新加坡", 
            "LineFrom": "cn-gd", 
            "LineTo": "sg", 
            "LineId": "line_cn_sg", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "sg", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_sg", 
                    "LineToName": "新加坡"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "sg", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_sg", 
                    "LineToName": "新加坡"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "sg", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "曼谷", 
            "LineFrom": "cn-bj2", 
            "LineTo": "th-bkk", 
            "LineId": "line_cn_th-bkk", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_th-bkk", 
                    "LineToName": "曼谷"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_th-bkk", 
                    "LineToName": "曼谷"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_th-bkk", 
                    "LineToName": "曼谷"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "中国台北", 
            "LineFrom": "cn-gd", 
            "LineTo": "tw-tp", 
            "LineId": "line_cn_tw-tp", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "tw-tp", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_tw-tp", 
                    "LineToName": "中国台北"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "tw-tp", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_tw-tp", 
                    "LineToName": "中国台北"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "tw-tp", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_tw-tp", 
                    "LineToName": "中国台北"
                }
            ]
        }, 
        {
            "LineFromName": "中国(多地)", 
            "LineToName": "华盛顿", 
            "LineFrom": "cn-gd", 
            "LineTo": "us-ws", 
            "LineId": "line_cn_us-ws", 
            "LineDetail": [
                {
                    "LineFromName": "中国华北", 
                    "LineTo": "us-ws", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_us-ws", 
                    "LineToName": "华盛顿"
                }, 
                {
                    "LineFromName": "中国华南", 
                    "LineTo": "us-ws", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_us-ws", 
                    "LineToName": "华盛顿"
                }, 
                {
                    "LineFromName": "中国华东", 
                    "LineTo": "us-ws", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_us-ws", 
                    "LineToName": "华盛顿"
                }
            ]
        }, 
        {
            "LineFromName": "法兰克福", 
            "LineToName": "中国", 
            "LineFrom": "ge-fra", 
            "LineTo": "cn-bj2", 
            "LineId": "line_ge-fra_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "法兰克福", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_cn-bj2", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "法兰克福", 
            "LineToName": "中国香港", 
            "LineFrom": "ge-fra", 
            "LineTo": "hk", 
            "LineId": "line_ge-fra_hk", 
            "LineDetail": [
                {
                    "LineFromName": "法兰克福", 
                    "LineTo": "hk", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "法兰克福", 
            "LineToName": "东京", 
            "LineFrom": "ge-fra", 
            "LineTo": "jpn-tky", 
            "LineId": "line_ge-fra_jpn-tky", 
            "LineDetail": [
                {
                    "LineFromName": "法兰克福", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_jpn-tky", 
                    "LineToName": "东京"
                }
            ]
        }, 
        {
            "LineFromName": "法兰克福", 
            "LineToName": "新加坡", 
            "LineFrom": "ge-fra", 
            "LineTo": "sg", 
            "LineId": "line_ge-fra_sg", 
            "LineDetail": [
                {
                    "LineFromName": "法兰克福", 
                    "LineTo": "sg", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "法兰克福", 
            "LineToName": "洛杉矶", 
            "LineFrom": "ge-fra", 
            "LineTo": "us-ca", 
            "LineId": "line_ge-fra_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "法兰克福", 
                    "LineTo": "us-ca", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "法兰克福", 
            "LineToName": "华盛顿", 
            "LineFrom": "ge-fra", 
            "LineTo": "us-ws", 
            "LineId": "line_ge-fra_us-ws", 
            "LineDetail": [
                {
                    "LineFromName": "法兰克福", 
                    "LineTo": "us-ws", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_us-ws", 
                    "LineToName": "华盛顿"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "中国", 
            "LineFrom": "hk", 
            "LineTo": "cn-gd", 
            "LineId": "line_hk_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_cn-gd", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "法兰克福", 
            "LineFrom": "hk", 
            "LineTo": "ge-fra", 
            "LineId": "line_hk_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_ge-fra", 
                    "LineToName": "法兰克福"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "雅加达", 
            "LineFrom": "hk", 
            "LineTo": "idn-jakarta", 
            "LineId": "line_hk_idn-jakarta", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_idn-jakarta", 
                    "LineToName": "雅加达"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "孟买", 
            "LineFrom": "hk", 
            "LineTo": "ind-mumbai", 
            "LineId": "line_hk_ind-mumbai", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_ind-mumbai", 
                    "LineToName": "孟买"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "东京", 
            "LineFrom": "hk", 
            "LineTo": "jpn-tky", 
            "LineId": "line_hk_jpn-tky", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_jpn-tky", 
                    "LineToName": "东京"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "莫斯科", 
            "LineFrom": "hk", 
            "LineTo": "rus-mosc", 
            "LineId": "line_hk_rus-mosc", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "rus-mosc", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_rus-mosc", 
                    "LineToName": "莫斯科"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "新加坡", 
            "LineFrom": "hk", 
            "LineTo": "sg", 
            "LineId": "line_hk_sg", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "sg", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "曼谷", 
            "LineFrom": "hk", 
            "LineTo": "th-bkk", 
            "LineId": "line_hk_th-bkk", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_th-bkk", 
                    "LineToName": "曼谷"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "中国台北", 
            "LineFrom": "hk", 
            "LineTo": "tw-tp", 
            "LineId": "line_hk_tw-tp", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "tw-tp", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_tw-tp", 
                    "LineToName": "中国台北"
                }
            ]
        }, 
        {
            "LineFromName": "中国香港", 
            "LineToName": "洛杉矶", 
            "LineFrom": "hk", 
            "LineTo": "us-ca", 
            "LineId": "line_hk_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "us-ca", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "雅加达", 
            "LineToName": "中国", 
            "LineFrom": "idn-jakarta", 
            "LineTo": "cn-gd", 
            "LineId": "line_idn-jakarta_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "雅加达", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "idn-jakarta", 
                    "LineId": "line_idn-jakarta_cn-gd", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "雅加达", 
            "LineToName": "中国香港", 
            "LineFrom": "idn-jakarta", 
            "LineTo": "hk", 
            "LineId": "line_idn-jakarta_hk", 
            "LineDetail": [
                {
                    "LineFromName": "雅加达", 
                    "LineTo": "hk", 
                    "LineFrom": "idn-jakarta", 
                    "LineId": "line_idn-jakarta_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "雅加达", 
            "LineToName": "新加坡", 
            "LineFrom": "idn-jakarta", 
            "LineTo": "sg", 
            "LineId": "line_idn-jakarta_sg", 
            "LineDetail": [
                {
                    "LineFromName": "亚太", 
                    "LineTo": "sg", 
                    "LineFrom": "idn-jakarta", 
                    "LineId": "line_idn-jakarta_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "孟买", 
            "LineToName": "中国", 
            "LineFrom": "ind-mumbai", 
            "LineTo": "cn-gd", 
            "LineId": "line_ind-mumbai_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "孟买", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "ind-mumbai", 
                    "LineId": "line_ind-mumbai_cn-gd", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "孟买", 
            "LineToName": "中国香港", 
            "LineFrom": "ind-mumbai", 
            "LineTo": "hk", 
            "LineId": "line_ind-mumbai_hk", 
            "LineDetail": [
                {
                    "LineFromName": "孟买", 
                    "LineTo": "hk", 
                    "LineFrom": "ind-mumbai", 
                    "LineId": "line_ind-mumbai_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "孟买", 
            "LineToName": "新加坡", 
            "LineFrom": "ind-mumbai", 
            "LineTo": "sg", 
            "LineId": "line_ind-mumbai_sg", 
            "LineDetail": [
                {
                    "LineFromName": "孟买", 
                    "LineTo": "sg", 
                    "LineFrom": "ind-mumbai", 
                    "LineId": "line_ind-mumbai_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "孟买", 
            "LineToName": "洛杉矶", 
            "LineFrom": "ind-mumbai", 
            "LineTo": "us-ca", 
            "LineId": "line_ind-mumbai_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "孟买", 
                    "LineTo": "us-ca", 
                    "LineFrom": "ind-mumbai", 
                    "LineId": "line_ind-mumbai_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "东京", 
            "LineToName": "中国", 
            "LineFrom": "jpn-tky", 
            "LineTo": "cn-sh2", 
            "LineId": "line_jpn-tky_cn-sh2", 
            "LineDetail": [
                {
                    "LineFromName": "东京", 
                    "LineTo": "cn-sh2", 
                    "LineFrom": "jpn-tky", 
                    "LineId": "line_jpn-tky_cn-sh2", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "东京", 
            "LineToName": "中国香港", 
            "LineFrom": "jpn-tky", 
            "LineTo": "hk", 
            "LineId": "line_jpn-tky_hk", 
            "LineDetail": [
                {
                    "LineFromName": "东京", 
                    "LineTo": "hk", 
                    "LineFrom": "jpn-tky", 
                    "LineId": "line_jpn-tky_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "东京", 
            "LineToName": "首尔", 
            "LineFrom": "jpn-tky", 
            "LineTo": "kr-seoul", 
            "LineId": "line_jpn-tky_kr-seoul", 
            "LineDetail": [
                {
                    "LineFromName": "东京", 
                    "LineTo": "kr-seoul", 
                    "LineFrom": "jpn-tky", 
                    "LineId": "line_jpn-tky_kr-seoul", 
                    "LineToName": "首尔"
                }
            ]
        }, 
        {
            "LineFromName": "东京", 
            "LineToName": "洛杉矶", 
            "LineFrom": "jpn-tky", 
            "LineTo": "us-ca", 
            "LineId": "line_jpn-tky_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "东京", 
                    "LineTo": "us-ca", 
                    "LineFrom": "jpn-tky", 
                    "LineId": "line_jpn-tky_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "首尔", 
            "LineToName": "洛杉矶", 
            "LineFrom": "kr-seoul", 
            "LineTo": "us-ca", 
            "LineId": "line_kr-seoul_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "首尔", 
                    "LineTo": "us-ca", 
                    "LineFrom": "kr-seoul", 
                    "LineId": "line_kr-seoul_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "莫斯科", 
            "LineToName": "中国", 
            "LineFrom": "rus-mosc", 
            "LineTo": "cn-bj2", 
            "LineId": "line_rus-mosc_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "莫斯科", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_cn-bj2", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "莫斯科", 
            "LineToName": "中国香港", 
            "LineFrom": "rus-mosc", 
            "LineTo": "hk", 
            "LineId": "line_rus-mosc_hk", 
            "LineDetail": [
                {
                    "LineFromName": "莫斯科", 
                    "LineTo": "hk", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "莫斯科", 
            "LineToName": "新加坡", 
            "LineFrom": "rus-mosc", 
            "LineTo": "sg", 
            "LineId": "line_rus-mosc_sg", 
            "LineDetail": [
                {
                    "LineFromName": "莫斯科", 
                    "LineTo": "sg", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "莫斯科", 
            "LineToName": "洛杉矶", 
            "LineFrom": "rus-mosc", 
            "LineTo": "us-ca", 
            "LineId": "line_rus-mosc_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "莫斯科", 
                    "LineTo": "us-ca", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "莫斯科", 
            "LineToName": "华盛顿", 
            "LineFrom": "rus-mosc", 
            "LineTo": "us-ws", 
            "LineId": "line_rus-mosc_us-ws", 
            "LineDetail": [
                {
                    "LineFromName": "莫斯科", 
                    "LineTo": "us-ws", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_us-ws", 
                    "LineToName": "华盛顿"
                }
            ]
        }, 
        {
            "LineFromName": "新加坡", 
            "LineToName": "中国", 
            "LineFrom": "sg", 
            "LineTo": "cn-gd", 
            "LineId": "line_sg_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "U新加坡", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_cn-gd", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "新加坡", 
            "LineToName": "法兰克福", 
            "LineFrom": "sg", 
            "LineTo": "ge-fra", 
            "LineId": "line_sg_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "U新加坡", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_ge-fra", 
                    "LineToName": "法兰克福"
                }
            ]
        }, 
        {
            "LineFromName": "新加坡", 
            "LineToName": "中国香港", 
            "LineFrom": "sg", 
            "LineTo": "hk", 
            "LineId": "line_sg_hk", 
            "LineDetail": [
                {
                    "LineFromName": "U新加坡", 
                    "LineTo": "hk", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "新加坡", 
            "LineToName": "雅加达", 
            "LineFrom": "sg", 
            "LineTo": "idn-jakarta", 
            "LineId": "line_sg_idn-jakarta", 
            "LineDetail": [
                {
                    "LineFromName": "U新加坡", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_idn-jakarta", 
                    "LineToName": "雅加达"
                }
            ]
        }, 
        {
            "LineFromName": "新加坡", 
            "LineToName": "孟买", 
            "LineFrom": "sg", 
            "LineTo": "ind-mumbai", 
            "LineId": "line_sg_ind-mumbai", 
            "LineDetail": [
                {
                    "LineFromName": "U新加坡", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_ind-mumbai", 
                    "LineToName": "孟买"
                }
            ]
        }, 
        {
            "LineFromName": "新加坡", 
            "LineToName": "曼谷", 
            "LineFrom": "sg", 
            "LineTo": "th-bkk", 
            "LineId": "line_sg_th-bkk", 
            "LineDetail": [
                {
                    "LineFromName": "U新加坡", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_th-bkk", 
                    "LineToName": "曼谷"
                }
            ]
        }, 
        {
            "LineFromName": "新加坡", 
            "LineToName": "洛杉矶", 
            "LineFrom": "sg", 
            "LineTo": "us-ca", 
            "LineId": "line_sg_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "U新加坡", 
                    "LineTo": "us-ca", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "曼谷", 
            "LineToName": "中国", 
            "LineFrom": "th-bkk", 
            "LineTo": "cn-gd", 
            "LineId": "line_th-bkk_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "曼谷", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "th-bkk", 
                    "LineId": "line_th-bkk_cn-gd", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "曼谷", 
            "LineToName": "中国香港", 
            "LineFrom": "th-bkk", 
            "LineTo": "hk", 
            "LineId": "line_th-bkk_hk", 
            "LineDetail": [
                {
                    "LineFromName": "曼谷", 
                    "LineTo": "hk", 
                    "LineFrom": "th-bkk", 
                    "LineId": "line_th-bkk_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "曼谷", 
            "LineToName": "新加坡", 
            "LineFrom": "th-bkk", 
            "LineTo": "sg", 
            "LineId": "line_th-bkk_sg", 
            "LineDetail": [
                {
                    "LineFromName": "曼谷", 
                    "LineTo": "sg", 
                    "LineFrom": "th-bkk", 
                    "LineId": "line_th-bkk_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "中国台北", 
            "LineToName": "中国", 
            "LineFrom": "tw-tp", 
            "LineTo": "cn-gd", 
            "LineId": "line_tw-tp_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "中国台北", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "tw-tp", 
                    "LineId": "line_tw-tp_cn-gd", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "中国台北", 
            "LineToName": "中国香港", 
            "LineFrom": "tw-tp", 
            "LineTo": "hk", 
            "LineId": "line_tw-tp_hk", 
            "LineDetail": [
                {
                    "LineFromName": "中国台北", 
                    "LineTo": "hk", 
                    "LineFrom": "tw-tp", 
                    "LineId": "line_tw-tp_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "中国台北", 
            "LineToName": "新加坡", 
            "LineFrom": "tw-tp", 
            "LineTo": "sg", 
            "LineId": "line_tw-tp_sg", 
            "LineDetail": [
                {
                    "LineFromName": "中国台北", 
                    "LineTo": "sg", 
                    "LineFrom": "tw-tp", 
                    "LineId": "line_tw-tp_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "中国台北", 
            "LineToName": "洛杉矶", 
            "LineFrom": "tw-tp", 
            "LineTo": "us-ca", 
            "LineId": "line_tw-tp_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "中国台北", 
                    "LineTo": "us-ca", 
                    "LineFrom": "tw-tp", 
                    "LineId": "line_tw-tp_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }, 
        {
            "LineFromName": "洛杉矶", 
            "LineToName": "中国", 
            "LineFrom": "us-ca", 
            "LineTo": "cn-bj2", 
            "LineId": "line_us-ca_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "洛杉矶", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_cn-bj2", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "洛杉矶", 
            "LineToName": "中国香港", 
            "LineFrom": "us-ca", 
            "LineTo": "hk", 
            "LineId": "line_us-ca_hk", 
            "LineDetail": [
                {
                    "LineFromName": "洛杉矶", 
                    "LineTo": "hk", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_hk", 
                    "LineToName": "中国香港"
                }
            ]
        }, 
        {
            "LineFromName": "洛杉矶", 
            "LineToName": "孟买", 
            "LineFrom": "us-ca", 
            "LineTo": "ind-mumbai", 
            "LineId": "line_us-ca_ind-mumbai", 
            "LineDetail": [
                {
                    "LineFromName": "洛杉矶", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_ind-mumbai", 
                    "LineToName": "孟买"
                }
            ]
        }, 
        {
            "LineFromName": "洛杉矶", 
            "LineToName": "东京", 
            "LineFrom": "us-ca", 
            "LineTo": "jpn-tky", 
            "LineId": "line_us-ca_jpn-tky", 
            "LineDetail": [
                {
                    "LineFromName": "洛杉矶", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_jpn-tky", 
                    "LineToName": "东京"
                }
            ]
        }, 
        {
            "LineFromName": "洛杉矶", 
            "LineToName": "新加坡", 
            "LineFrom": "us-ca", 
            "LineTo": "sg", 
            "LineId": "line_us-ca_sg", 
            "LineDetail": [
                {
                    "LineFromName": "洛杉矶", 
                    "LineTo": "sg", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_sg", 
                    "LineToName": "新加坡"
                }
            ]
        }, 
        {
            "LineFromName": "洛杉矶", 
            "LineToName": "华盛顿", 
            "LineFrom": "us-ca", 
            "LineTo": "us-ws", 
            "LineId": "line_us-ca_us-ws", 
            "LineDetail": [
                {
                    "LineFromName": "洛杉矶", 
                    "LineTo": "us-ws", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_us-ws", 
                    "LineToName": "华盛顿"
                }
            ]
        }, 
        {
            "LineFromName": "华盛顿", 
            "LineToName": "中国", 
            "LineFrom": "us-ws", 
            "LineTo": "cn-bj2", 
            "LineId": "line_us-ws_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "华盛顿", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "us-ws", 
                    "LineId": "line_us-ws_cn-bj2", 
                    "LineToName": "中国"
                }
            ]
        }, 
        {
            "LineFromName": "华盛顿", 
            "LineToName": "法兰克福", 
            "LineFrom": "us-ws", 
            "LineTo": "ge-fra", 
            "LineId": "line_us-ws_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "华盛顿", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "us-ws", 
                    "LineId": "line_us-ws_ge-fra", 
                    "LineToName": "法兰克福"
                }
            ]
        }, 
        {
            "LineFromName": "华盛顿", 
            "LineToName": "洛杉矶", 
            "LineFrom": "us-ws", 
            "LineTo": "us-ca", 
            "LineId": "line_us-ws_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "华盛顿", 
                    "LineTo": "us-ca", 
                    "LineFrom": "us-ws", 
                    "LineId": "line_us-ws_us-ca", 
                    "LineToName": "洛杉矶"
                }
            ]
        }
    ], 
    "Message": "", 
    "RetCode": 0
}
```

