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
            "LineFromName": "\u62c9\u5404\u65af", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "afr-nigeria", 
            "LineTo": "cn-bj2", 
            "LineId": "line_afr-nigeria_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "\u62c9\u5404\u65af", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "afr-nigeria", 
                    "LineId": "line_afr-nigeria_cn-bj2", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u62c9\u5404\u65af", 
            "LineToName": "\u6cd5\u5170\u514b\u798f", 
            "LineFrom": "afr-nigeria", 
            "LineTo": "ge-fra", 
            "LineId": "line_afr-nigeria_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "\u62c9\u5404\u65af", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "afr-nigeria", 
                    "LineId": "line_afr-nigeria_ge-fra", 
                    "LineToName": "\u6cd5\u5170\u514b\u798f"
                }
            ]
        }, 
        {
            "LineFromName": "\u5723\u4fdd\u7f57", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "bra-saopaulo", 
            "LineTo": "us-ca", 
            "LineId": "line_bra-saopaulo_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u5723\u4fdd\u7f57", 
                    "LineTo": "us-ca", 
                    "LineFrom": "bra-saopaulo", 
                    "LineId": "line_bra-saopaulo_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd", 
            "LineToName": "\u6cd5\u5170\u514b\u798f", 
            "LineFrom": "cn-bj2", 
            "LineTo": "ge-fra", 
            "LineId": "line_cn-bj2_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_ge-fra", 
                    "LineToName": "\u6cd5\u5170\u514b\u798f"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "cn-bj2", 
            "LineTo": "us-ca", 
            "LineId": "line_cn-bj2_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd", 
                    "LineTo": "us-ca", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "cn-gd", 
            "LineTo": "hk", 
            "LineId": "line_cn-gd_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd", 
                    "LineTo": "hk", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u6cd5\u5170\u514b\u798f", 
            "LineFrom": "cn-gd", 
            "LineTo": "ge-fra", 
            "LineId": "line_cn-ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_ge-fra", 
                    "LineToName": "\u6cd5\u5170\u514b\u798f"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_ge-fra", 
                    "LineToName": "\u6cd5\u5170\u514b\u798f"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_ge-fra", 
                    "LineToName": "\u6cd5\u5170\u514b\u798f"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "cn-gd", 
            "LineTo": "hk", 
            "LineId": "line_cn-hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "hk", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "hk", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "hk", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "cn-gd", 
            "LineTo": "us-ca", 
            "LineId": "line_cn-us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "us-ca", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "us-ca", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "us-ca", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u62c9\u5404\u65af", 
            "LineFrom": "cn-gd", 
            "LineTo": "afr-nigeria", 
            "LineId": "line_cn_afr-nigeria", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "afr-nigeria", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_afr-nigeria", 
                    "LineToName": "\u62c9\u5404\u65af"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "afr-nigeria", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_afr-nigeria", 
                    "LineToName": "\u62c9\u5404\u65af"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "afr-nigeria", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_afr-nigeria", 
                    "LineToName": "\u62c9\u5404\u65af"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u96c5\u52a0\u8fbe", 
            "LineFrom": "cn-gd", 
            "LineTo": "idn-jakarta", 
            "LineId": "line_cn_idn-jakarta", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_idn-jakarta", 
                    "LineToName": "\u96c5\u52a0\u8fbe"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_idn-jakarta", 
                    "LineToName": "\u96c5\u52a0\u8fbe"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_idn-jakarta", 
                    "LineToName": "\u96c5\u52a0\u8fbe"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u5b5f\u4e70", 
            "LineFrom": "cn-gd", 
            "LineTo": "ind-mumbai", 
            "LineId": "line_cn_ind-mumbai", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_ind-mumbai", 
                    "LineToName": "\u5b5f\u4e70"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_ind-mumbai", 
                    "LineToName": "\u5b5f\u4e70"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_ind-mumbai", 
                    "LineToName": "\u5b5f\u4e70"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u4e1c\u4eac", 
            "LineFrom": "cn-gd", 
            "LineTo": "jpn-tky", 
            "LineId": "line_cn_jpn-tky", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_jpn-tky", 
                    "LineToName": "\u4e1c\u4eac"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_jpn-tky", 
                    "LineToName": "\u4e1c\u4eac"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_jpn-tky", 
                    "LineToName": "\u4e1c\u4eac"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u83ab\u65af\u79d1", 
            "LineFrom": "cn-gd", 
            "LineTo": "rus-mosc", 
            "LineId": "line_cn_rus-mosc", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "rus-mosc", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_rus-mosc", 
                    "LineToName": "\u83ab\u65af\u79d1"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "rus-mosc", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_rus-mosc", 
                    "LineToName": "\u83ab\u65af\u79d1"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "rus-mosc", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_rus-mosc", 
                    "LineToName": "\u83ab\u65af\u79d1"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "cn-gd", 
            "LineTo": "sg", 
            "LineId": "line_cn_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "sg", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "sg", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "sg", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u66fc\u8c37", 
            "LineFrom": "cn-bj2", 
            "LineTo": "th-bkk", 
            "LineId": "line_cn_th-bkk", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_th-bkk", 
                    "LineToName": "\u66fc\u8c37"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_th-bkk", 
                    "LineToName": "\u66fc\u8c37"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_th-bkk", 
                    "LineToName": "\u66fc\u8c37"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u4e2d\u56fd\u53f0\u5317", 
            "LineFrom": "cn-gd", 
            "LineTo": "tw-tp", 
            "LineId": "line_cn_tw-tp", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "tw-tp", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_tw-tp", 
                    "LineToName": "\u4e2d\u56fd\u53f0\u5317"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "tw-tp", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_tw-tp", 
                    "LineToName": "\u4e2d\u56fd\u53f0\u5317"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "tw-tp", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_tw-tp", 
                    "LineToName": "\u4e2d\u56fd\u53f0\u5317"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "LineToName": "\u534e\u76db\u987f", 
            "LineFrom": "cn-gd", 
            "LineTo": "us-ws", 
            "LineId": "line_cn_us-ws", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5317", 
                    "LineTo": "us-ws", 
                    "LineFrom": "cn-bj2", 
                    "LineId": "line_cn-bj2_us-ws", 
                    "LineToName": "\u534e\u76db\u987f"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u5357", 
                    "LineTo": "us-ws", 
                    "LineFrom": "cn-gd", 
                    "LineId": "line_cn-gd_us-ws", 
                    "LineToName": "\u534e\u76db\u987f"
                }, 
                {
                    "LineFromName": "\u4e2d\u56fd\u534e\u4e1c", 
                    "LineTo": "us-ws", 
                    "LineFrom": "cn-sh2", 
                    "LineId": "line_cn-sh2_us-ws", 
                    "LineToName": "\u534e\u76db\u987f"
                }
            ]
        }, 
        {
            "LineFromName": "\u6cd5\u5170\u514b\u798f", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "ge-fra", 
            "LineTo": "cn-bj2", 
            "LineId": "line_ge-fra_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "\u6cd5\u5170\u514b\u798f", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_cn-bj2", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u6cd5\u5170\u514b\u798f", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "ge-fra", 
            "LineTo": "hk", 
            "LineId": "line_ge-fra_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u6cd5\u5170\u514b\u798f", 
                    "LineTo": "hk", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u6cd5\u5170\u514b\u798f", 
            "LineToName": "\u4e1c\u4eac", 
            "LineFrom": "ge-fra", 
            "LineTo": "jpn-tky", 
            "LineId": "line_ge-fra_jpn-tky", 
            "LineDetail": [
                {
                    "LineFromName": "\u6cd5\u5170\u514b\u798f", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_jpn-tky", 
                    "LineToName": "\u4e1c\u4eac"
                }
            ]
        }, 
        {
            "LineFromName": "\u6cd5\u5170\u514b\u798f", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "ge-fra", 
            "LineTo": "sg", 
            "LineId": "line_ge-fra_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u6cd5\u5170\u514b\u798f", 
                    "LineTo": "sg", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u6cd5\u5170\u514b\u798f", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "ge-fra", 
            "LineTo": "us-ca", 
            "LineId": "line_ge-fra_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u6cd5\u5170\u514b\u798f", 
                    "LineTo": "us-ca", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u6cd5\u5170\u514b\u798f", 
            "LineToName": "\u534e\u76db\u987f", 
            "LineFrom": "ge-fra", 
            "LineTo": "us-ws", 
            "LineId": "line_ge-fra_us-ws", 
            "LineDetail": [
                {
                    "LineFromName": "\u6cd5\u5170\u514b\u798f", 
                    "LineTo": "us-ws", 
                    "LineFrom": "ge-fra", 
                    "LineId": "line_ge-fra_us-ws", 
                    "LineToName": "\u534e\u76db\u987f"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "hk", 
            "LineTo": "cn-gd", 
            "LineId": "line_hk_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_cn-gd", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u6cd5\u5170\u514b\u798f", 
            "LineFrom": "hk", 
            "LineTo": "ge-fra", 
            "LineId": "line_hk_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_ge-fra", 
                    "LineToName": "\u6cd5\u5170\u514b\u798f"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u96c5\u52a0\u8fbe", 
            "LineFrom": "hk", 
            "LineTo": "idn-jakarta", 
            "LineId": "line_hk_idn-jakarta", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_idn-jakarta", 
                    "LineToName": "\u96c5\u52a0\u8fbe"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u5b5f\u4e70", 
            "LineFrom": "hk", 
            "LineTo": "ind-mumbai", 
            "LineId": "line_hk_ind-mumbai", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_ind-mumbai", 
                    "LineToName": "\u5b5f\u4e70"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u4e1c\u4eac", 
            "LineFrom": "hk", 
            "LineTo": "jpn-tky", 
            "LineId": "line_hk_jpn-tky", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_jpn-tky", 
                    "LineToName": "\u4e1c\u4eac"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u83ab\u65af\u79d1", 
            "LineFrom": "hk", 
            "LineTo": "rus-mosc", 
            "LineId": "line_hk_rus-mosc", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "rus-mosc", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_rus-mosc", 
                    "LineToName": "\u83ab\u65af\u79d1"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "hk", 
            "LineTo": "sg", 
            "LineId": "line_hk_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "sg", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u66fc\u8c37", 
            "LineFrom": "hk", 
            "LineTo": "th-bkk", 
            "LineId": "line_hk_th-bkk", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_th-bkk", 
                    "LineToName": "\u66fc\u8c37"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u4e2d\u56fd\u53f0\u5317", 
            "LineFrom": "hk", 
            "LineTo": "tw-tp", 
            "LineId": "line_hk_tw-tp", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "tw-tp", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_tw-tp", 
                    "LineToName": "\u4e2d\u56fd\u53f0\u5317"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "hk", 
            "LineTo": "us-ca", 
            "LineId": "line_hk_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "us-ca", 
                    "LineFrom": "hk", 
                    "LineId": "line_hk_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u96c5\u52a0\u8fbe", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "idn-jakarta", 
            "LineTo": "cn-gd", 
            "LineId": "line_idn-jakarta_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "\u96c5\u52a0\u8fbe", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "idn-jakarta", 
                    "LineId": "line_idn-jakarta_cn-gd", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u96c5\u52a0\u8fbe", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "idn-jakarta", 
            "LineTo": "hk", 
            "LineId": "line_idn-jakarta_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u96c5\u52a0\u8fbe", 
                    "LineTo": "hk", 
                    "LineFrom": "idn-jakarta", 
                    "LineId": "line_idn-jakarta_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u96c5\u52a0\u8fbe", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "idn-jakarta", 
            "LineTo": "sg", 
            "LineId": "line_idn-jakarta_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineTo": "sg", 
                    "LineFrom": "idn-jakarta", 
                    "LineId": "line_idn-jakarta_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u5b5f\u4e70", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "ind-mumbai", 
            "LineTo": "cn-gd", 
            "LineId": "line_ind-mumbai_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "\u5b5f\u4e70", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "ind-mumbai", 
                    "LineId": "line_ind-mumbai_cn-gd", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u5b5f\u4e70", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "ind-mumbai", 
            "LineTo": "hk", 
            "LineId": "line_ind-mumbai_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u5b5f\u4e70", 
                    "LineTo": "hk", 
                    "LineFrom": "ind-mumbai", 
                    "LineId": "line_ind-mumbai_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u5b5f\u4e70", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "ind-mumbai", 
            "LineTo": "sg", 
            "LineId": "line_ind-mumbai_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u5b5f\u4e70", 
                    "LineTo": "sg", 
                    "LineFrom": "ind-mumbai", 
                    "LineId": "line_ind-mumbai_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u5b5f\u4e70", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "ind-mumbai", 
            "LineTo": "us-ca", 
            "LineId": "line_ind-mumbai_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u5b5f\u4e70", 
                    "LineTo": "us-ca", 
                    "LineFrom": "ind-mumbai", 
                    "LineId": "line_ind-mumbai_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e1c\u4eac", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "jpn-tky", 
            "LineTo": "cn-sh2", 
            "LineId": "line_jpn-tky_cn-sh2", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e1c\u4eac", 
                    "LineTo": "cn-sh2", 
                    "LineFrom": "jpn-tky", 
                    "LineId": "line_jpn-tky_cn-sh2", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e1c\u4eac", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "jpn-tky", 
            "LineTo": "hk", 
            "LineId": "line_jpn-tky_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e1c\u4eac", 
                    "LineTo": "hk", 
                    "LineFrom": "jpn-tky", 
                    "LineId": "line_jpn-tky_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e1c\u4eac", 
            "LineToName": "\u9996\u5c14", 
            "LineFrom": "jpn-tky", 
            "LineTo": "kr-seoul", 
            "LineId": "line_jpn-tky_kr-seoul", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e1c\u4eac", 
                    "LineTo": "kr-seoul", 
                    "LineFrom": "jpn-tky", 
                    "LineId": "line_jpn-tky_kr-seoul", 
                    "LineToName": "\u9996\u5c14"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e1c\u4eac", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "jpn-tky", 
            "LineTo": "us-ca", 
            "LineId": "line_jpn-tky_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e1c\u4eac", 
                    "LineTo": "us-ca", 
                    "LineFrom": "jpn-tky", 
                    "LineId": "line_jpn-tky_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u9996\u5c14", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "kr-seoul", 
            "LineTo": "us-ca", 
            "LineId": "line_kr-seoul_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u9996\u5c14", 
                    "LineTo": "us-ca", 
                    "LineFrom": "kr-seoul", 
                    "LineId": "line_kr-seoul_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u83ab\u65af\u79d1", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "rus-mosc", 
            "LineTo": "cn-bj2", 
            "LineId": "line_rus-mosc_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "\u83ab\u65af\u79d1", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_cn-bj2", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u83ab\u65af\u79d1", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "rus-mosc", 
            "LineTo": "hk", 
            "LineId": "line_rus-mosc_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u83ab\u65af\u79d1", 
                    "LineTo": "hk", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u83ab\u65af\u79d1", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "rus-mosc", 
            "LineTo": "sg", 
            "LineId": "line_rus-mosc_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u83ab\u65af\u79d1", 
                    "LineTo": "sg", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u83ab\u65af\u79d1", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "rus-mosc", 
            "LineTo": "us-ca", 
            "LineId": "line_rus-mosc_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u83ab\u65af\u79d1", 
                    "LineTo": "us-ca", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u83ab\u65af\u79d1", 
            "LineToName": "\u534e\u76db\u987f", 
            "LineFrom": "rus-mosc", 
            "LineTo": "us-ws", 
            "LineId": "line_rus-mosc_us-ws", 
            "LineDetail": [
                {
                    "LineFromName": "\u83ab\u65af\u79d1", 
                    "LineTo": "us-ws", 
                    "LineFrom": "rus-mosc", 
                    "LineId": "line_rus-mosc_us-ws", 
                    "LineToName": "\u534e\u76db\u987f"
                }
            ]
        }, 
        {
            "LineFromName": "\u65b0\u52a0\u5761", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "sg", 
            "LineTo": "cn-gd", 
            "LineId": "line_sg_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "U\u65b0\u52a0\u5761", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_cn-gd", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u65b0\u52a0\u5761", 
            "LineToName": "\u6cd5\u5170\u514b\u798f", 
            "LineFrom": "sg", 
            "LineTo": "ge-fra", 
            "LineId": "line_sg_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "U\u65b0\u52a0\u5761", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_ge-fra", 
                    "LineToName": "\u6cd5\u5170\u514b\u798f"
                }
            ]
        }, 
        {
            "LineFromName": "\u65b0\u52a0\u5761", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "sg", 
            "LineTo": "hk", 
            "LineId": "line_sg_hk", 
            "LineDetail": [
                {
                    "LineFromName": "U\u65b0\u52a0\u5761", 
                    "LineTo": "hk", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u65b0\u52a0\u5761", 
            "LineToName": "\u96c5\u52a0\u8fbe", 
            "LineFrom": "sg", 
            "LineTo": "idn-jakarta", 
            "LineId": "line_sg_idn-jakarta", 
            "LineDetail": [
                {
                    "LineFromName": "U\u65b0\u52a0\u5761", 
                    "LineTo": "idn-jakarta", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_idn-jakarta", 
                    "LineToName": "\u96c5\u52a0\u8fbe"
                }
            ]
        }, 
        {
            "LineFromName": "\u65b0\u52a0\u5761", 
            "LineToName": "\u5b5f\u4e70", 
            "LineFrom": "sg", 
            "LineTo": "ind-mumbai", 
            "LineId": "line_sg_ind-mumbai", 
            "LineDetail": [
                {
                    "LineFromName": "U\u65b0\u52a0\u5761", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_ind-mumbai", 
                    "LineToName": "\u5b5f\u4e70"
                }
            ]
        }, 
        {
            "LineFromName": "\u65b0\u52a0\u5761", 
            "LineToName": "\u66fc\u8c37", 
            "LineFrom": "sg", 
            "LineTo": "th-bkk", 
            "LineId": "line_sg_th-bkk", 
            "LineDetail": [
                {
                    "LineFromName": "U\u65b0\u52a0\u5761", 
                    "LineTo": "th-bkk", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_th-bkk", 
                    "LineToName": "\u66fc\u8c37"
                }
            ]
        }, 
        {
            "LineFromName": "\u65b0\u52a0\u5761", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "sg", 
            "LineTo": "us-ca", 
            "LineId": "line_sg_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "U\u65b0\u52a0\u5761", 
                    "LineTo": "us-ca", 
                    "LineFrom": "sg", 
                    "LineId": "line_sg_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u66fc\u8c37", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "th-bkk", 
            "LineTo": "cn-gd", 
            "LineId": "line_th-bkk_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "\u66fc\u8c37", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "th-bkk", 
                    "LineId": "line_th-bkk_cn-gd", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u66fc\u8c37", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "th-bkk", 
            "LineTo": "hk", 
            "LineId": "line_th-bkk_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u66fc\u8c37", 
                    "LineTo": "hk", 
                    "LineFrom": "th-bkk", 
                    "LineId": "line_th-bkk_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u66fc\u8c37", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "th-bkk", 
            "LineTo": "sg", 
            "LineId": "line_th-bkk_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u66fc\u8c37", 
                    "LineTo": "sg", 
                    "LineFrom": "th-bkk", 
                    "LineId": "line_th-bkk_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u53f0\u5317", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "tw-tp", 
            "LineTo": "cn-gd", 
            "LineId": "line_tw-tp_cn-gd", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u53f0\u5317", 
                    "LineTo": "cn-gd", 
                    "LineFrom": "tw-tp", 
                    "LineId": "line_tw-tp_cn-gd", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u53f0\u5317", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "tw-tp", 
            "LineTo": "hk", 
            "LineId": "line_tw-tp_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u53f0\u5317", 
                    "LineTo": "hk", 
                    "LineFrom": "tw-tp", 
                    "LineId": "line_tw-tp_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u53f0\u5317", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "tw-tp", 
            "LineTo": "sg", 
            "LineId": "line_tw-tp_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u53f0\u5317", 
                    "LineTo": "sg", 
                    "LineFrom": "tw-tp", 
                    "LineId": "line_tw-tp_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u53f0\u5317", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "tw-tp", 
            "LineTo": "us-ca", 
            "LineId": "line_tw-tp_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e2d\u56fd\u53f0\u5317", 
                    "LineTo": "us-ca", 
                    "LineFrom": "tw-tp", 
                    "LineId": "line_tw-tp_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }, 
        {
            "LineFromName": "\u6d1b\u6749\u77f6", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "us-ca", 
            "LineTo": "cn-bj2", 
            "LineId": "line_us-ca_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "\u6d1b\u6749\u77f6", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_cn-bj2", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u6d1b\u6749\u77f6", 
            "LineToName": "\u4e2d\u56fd\u9999\u6e2f", 
            "LineFrom": "us-ca", 
            "LineTo": "hk", 
            "LineId": "line_us-ca_hk", 
            "LineDetail": [
                {
                    "LineFromName": "\u6d1b\u6749\u77f6", 
                    "LineTo": "hk", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_hk", 
                    "LineToName": "\u4e2d\u56fd\u9999\u6e2f"
                }
            ]
        }, 
        {
            "LineFromName": "\u6d1b\u6749\u77f6", 
            "LineToName": "\u5b5f\u4e70", 
            "LineFrom": "us-ca", 
            "LineTo": "ind-mumbai", 
            "LineId": "line_us-ca_ind-mumbai", 
            "LineDetail": [
                {
                    "LineFromName": "\u6d1b\u6749\u77f6", 
                    "LineTo": "ind-mumbai", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_ind-mumbai", 
                    "LineToName": "\u5b5f\u4e70"
                }
            ]
        }, 
        {
            "LineFromName": "\u6d1b\u6749\u77f6", 
            "LineToName": "\u4e1c\u4eac", 
            "LineFrom": "us-ca", 
            "LineTo": "jpn-tky", 
            "LineId": "line_us-ca_jpn-tky", 
            "LineDetail": [
                {
                    "LineFromName": "\u6d1b\u6749\u77f6", 
                    "LineTo": "jpn-tky", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_jpn-tky", 
                    "LineToName": "\u4e1c\u4eac"
                }
            ]
        }, 
        {
            "LineFromName": "\u6d1b\u6749\u77f6", 
            "LineToName": "\u65b0\u52a0\u5761", 
            "LineFrom": "us-ca", 
            "LineTo": "sg", 
            "LineId": "line_us-ca_sg", 
            "LineDetail": [
                {
                    "LineFromName": "\u6d1b\u6749\u77f6", 
                    "LineTo": "sg", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_sg", 
                    "LineToName": "\u65b0\u52a0\u5761"
                }
            ]
        }, 
        {
            "LineFromName": "\u6d1b\u6749\u77f6", 
            "LineToName": "\u534e\u76db\u987f", 
            "LineFrom": "us-ca", 
            "LineTo": "us-ws", 
            "LineId": "line_us-ca_us-ws", 
            "LineDetail": [
                {
                    "LineFromName": "\u6d1b\u6749\u77f6", 
                    "LineTo": "us-ws", 
                    "LineFrom": "us-ca", 
                    "LineId": "line_us-ca_us-ws", 
                    "LineToName": "\u534e\u76db\u987f"
                }
            ]
        }, 
        {
            "LineFromName": "\u534e\u76db\u987f", 
            "LineToName": "\u4e2d\u56fd", 
            "LineFrom": "us-ws", 
            "LineTo": "cn-bj2", 
            "LineId": "line_us-ws_cn-bj2", 
            "LineDetail": [
                {
                    "LineFromName": "\u534e\u76db\u987f", 
                    "LineTo": "cn-bj2", 
                    "LineFrom": "us-ws", 
                    "LineId": "line_us-ws_cn-bj2", 
                    "LineToName": "\u4e2d\u56fd"
                }
            ]
        }, 
        {
            "LineFromName": "\u534e\u76db\u987f", 
            "LineToName": "\u6cd5\u5170\u514b\u798f", 
            "LineFrom": "us-ws", 
            "LineTo": "ge-fra", 
            "LineId": "line_us-ws_ge-fra", 
            "LineDetail": [
                {
                    "LineFromName": "\u534e\u76db\u987f", 
                    "LineTo": "ge-fra", 
                    "LineFrom": "us-ws", 
                    "LineId": "line_us-ws_ge-fra", 
                    "LineToName": "\u6cd5\u5170\u514b\u798f"
                }
            ]
        }, 
        {
            "LineFromName": "\u534e\u76db\u987f", 
            "LineToName": "\u6d1b\u6749\u77f6", 
            "LineFrom": "us-ws", 
            "LineTo": "us-ca", 
            "LineId": "line_us-ws_us-ca", 
            "LineDetail": [
                {
                    "LineFromName": "\u534e\u76db\u987f", 
                    "LineTo": "us-ca", 
                    "LineFrom": "us-ws", 
                    "LineId": "line_us-ws_us-ca", 
                    "LineToName": "\u6d1b\u6749\u77f6"
                }
            ]
        }
    ], 
    "Message": "", 
    "RetCode": 0
}
```

