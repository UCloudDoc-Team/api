# 获取全球加速服务加速配置信息-DescribeUGAInstance

获取全球加速服务加速配置信息，指定实例ID返回单个实例。未指定实例ID时 指定分页参数 则按创建时间降序 返回记录

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|UGAId|string|全球加速实例ID，如果传了实例ID 最多返回一条记录|No|
|Limit|int|返回的最大条数，默认为100，最大值400|No|
|Offset|int|偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UGAList|array|全球加速实例信息列表|No|
|TotalCount|int|符合条件的总数|No|

## UGAAInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UGAId|string|加速配置实例ID|**Yes**|
|CName|string|加速域名，请在加速区域配置您的业务域名的CName记录值为加速域名|**Yes**|
|UGAName|string|加速配置名称|**Yes**|
|IPList|array|源站IP列表，多个值由半角英文逗号相隔|No|
|Domain|string|源站域名|No|
|Location|string|源站所在区域，加速实例在绑定线路后会自动设置该值。console页面上通过该值过滤加速实例可以绑定的upath实例。注意：缺少该值会导致在console上无法修改线路|No|
|UPathSet|array|绑定的加速线路|No|
|TaskSet|array|端口配置信息（不再维护，建议使用ForwarderSet）|No|
|L4ForwarderSet|array|UGA 4层转发器配置，记录接入或回源端口，接入或回源协议信息|No|
|L7ForwarderSet|array|UGA 7层转发器配置，记录接入或回源端口，接入或回源协议信息 如绑定证书会返回证书ID|No|
|OutPublicIpList|array|线路出口IP地址|No|

## UPathSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UPathName|string|UPath名字|No|
|UPathId|string|UPath 实例ID|No|
|Bandwidth|int|带宽 Mbps, 1~800Mbps|No|
|LineId|string|线路ID|No|
|LineFromName|string|线路起点中文名字，加速区域|No|
|LineToName|string|线路对端中文名字，源站区域|No|
|LineFrom|string|线路起点英文代号，加速区域|No|
|LineTo|string|线路对端英文代号，源站区域|No|

## UGAATask
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Port|int|接入端口|**Yes**|
|Protocol|string|转发协议，枚举值["TCP"，"UDP"，"HTTPHTTP"，"HTTPSHTTP"，"HTTPSHTTPS"]。TCP和UDP代表四层转发，其余为七层转发|**Yes**|

## UGAL4Forwarder
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Port|int|接入端口|**Yes**|
|Protocol|string|转发协议，枚举值["TCP"，"UDP"，"HTTPHTTP"，"HTTPSHTTP"，"HTTPSHTTPS"]。TCP和UDP代表四层转发，其余为七层转发|**Yes**|
|RSPort|int|RSPort，源站监听端口|**Yes**|

## UGAL7Forwarder
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Port|int|接入端口|**Yes**|
|Protocol|string|转发协议，枚举值["TCP"，"UDP"，"HTTPHTTP"，"HTTPSHTTP"，"HTTPSHTTPS"]。TCP和UDP代表四层转发，其余为七层转发|**Yes**|
|RSPort|int|RSPort，源站监听端口|**Yes**|
|SSLId|string|证书ID|No|
|SSLName|string|证书名称|No|

## OutPublicIpInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IP|string| 线路出口EIP|No|
|Area|string|线路出口机房代号|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUGAInstance
&UGAAId=XmkZtPSH
&Limit=6
&Offset=9
&Limit=6
&Offset=8
&Limit=1
&Offset=6
```

# Response Example
```
{
    "Action": "DescribeUGAInstanceResponse", 
    "TotalCount": 9, 
    "RetCode": 0, 
    "UGAAList": [
        {
            "UPathSet": [
                {
                    "UPathId": "hfLvoPvb", 
                    "LineFromName": "gLRkKlEB", 
                    "LineToName": "ZgUeWUzT", 
                    "UPathName": "wNnRNrku", 
                    "Bandwidth": "rPTqsVYH", 
                    "LineId": "QSlKwEGP"
                }, 
                {
                    "UPathId": "IoYxMzab", 
                    "LineFromName": "dQXZZbvx", 
                    "LineToName": "RYngGVgG", 
                    "UPathName": "BBflCktv", 
                    "Bandwidth": "NiOZQHYU", 
                    "LineId": "dwvzUUkl"
                }, 
                {
                    "UPathId": "xVXNNuvx", 
                    "LineFromName": "TedEEDqU", 
                    "LineToName": "eTttEeyj", 
                    "UPathName": "pqXJKJyy", 
                    "Bandwidth": "hqCNztzE", 
                    "LineId": "xZbnEFqD"
                }, 
                {
                    "UPathId": "ZBWbnfuf", 
                    "LineFromName": "pLVRTzDI", 
                    "LineToName": "QaWNIFiO", 
                    "UPathName": "mbDbLnPy", 
                    "Bandwidth": "wthyrTEz", 
                    "LineId": "jBnhzwlp"
                }, 
                {
                    "UPathId": "xyGQXEhR", 
                    "LineFromName": "IbBkgukA", 
                    "LineToName": "fEUmYEBY", 
                    "UPathName": "XuKLeAsG", 
                    "Bandwidth": "dhmApITO", 
                    "LineId": "EohDrHhz"
                }, 
                {
                    "UPathId": "GJqtFPVn", 
                    "LineFromName": "hqxnNOOf", 
                    "LineToName": "PxBEiWmD", 
                    "UPathName": "FoJHBqDb", 
                    "Bandwidth": "IhGUeLSz", 
                    "LineId": "xrprvzwg"
                }, 
                {
                    "UPathId": "SjSwgoUu", 
                    "LineFromName": "DxXSHcoN", 
                    "LineToName": "HZVPkoQW", 
                    "UPathName": "YpaEVQrc", 
                    "Bandwidth": "ydCreYRE", 
                    "LineId": "bSdPzRzx"
                }
            ], 
            "Domain": "QiYPcsKi", 
            "ChargeType": "oxhYcPKK", 
            "UGAAName": "jbEJpJYC", 
            "ExpireTime": "rCNjUpbg", 
            "CName": "khtvqXXg", 
            "TaskSet": [
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 8
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 8
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }
            ], 
            "UGAAId": "KgqOlvzl", 
            "IPList": [
                "ZfyJZQTt", 
                "mbPrUxEX", 
                "ZPbosoSa", 
                "RffKkiNu", 
                "RcMxwzba", 
                "SoWMwEWn", 
                "CRxvTbEs", 
                "eXLoYOYp"
            ], 
            "CreateTime": "djGlCqZu"
        }, 
        {
            "UPathSet": [
                {
                    "UPathId": "dBAiqjMn", 
                    "LineFromName": "bUNJpCAa", 
                    "LineToName": "UvBJJuCL", 
                    "UPathName": "OYgGCQRJ", 
                    "Bandwidth": "GfHBRsBA", 
                    "LineId": "RQDVqliw"
                }, 
                {
                    "UPathId": "dNOvWqFz", 
                    "LineFromName": "vjZmoyml", 
                    "LineToName": "FlrHvDoT", 
                    "UPathName": "JlFjMulI", 
                    "Bandwidth": "ZJRmsada", 
                    "LineId": "vxfmGsIU"
                }, 
                {
                    "UPathId": "XsbKsHwO", 
                    "LineFromName": "WaydAShZ", 
                    "LineToName": "xQYwvwpS", 
                    "UPathName": "lyOBDPIG", 
                    "Bandwidth": "saMNQpAE", 
                    "LineId": "bBJRelLq"
                }, 
                {
                    "UPathId": "yROWZUuM", 
                    "LineFromName": "HyOgAgIE", 
                    "LineToName": "gZzUvBug", 
                    "UPathName": "DKbVdrsU", 
                    "Bandwidth": "mscOEwBc", 
                    "LineId": "uKvUoErv"
                }, 
                {
                    "UPathId": "krVCPiIw", 
                    "LineFromName": "WXWECgkK", 
                    "LineToName": "MkWXBAdp", 
                    "UPathName": "YjKagUfk", 
                    "Bandwidth": "iHenXYwx", 
                    "LineId": "YYgbAPYB"
                }, 
                {
                    "UPathId": "OjRCSMuA", 
                    "LineFromName": "BUACrGEv", 
                    "LineToName": "JdNohqJr", 
                    "UPathName": "LEcVRIxs", 
                    "Bandwidth": "BzeCfqus", 
                    "LineId": "TyDNDeVd"
                }, 
                {
                    "UPathId": "vEWBKSUk", 
                    "LineFromName": "msfNUceC", 
                    "LineToName": "bmEdMVQn", 
                    "UPathName": "pEzFLXMN", 
                    "Bandwidth": "TydyzEkx", 
                    "LineId": "JuClYkWr"
                }
            ], 
            "Domain": "BEZENhtW", 
            "ChargeType": "pfoAcyjR", 
            "UGAAName": "YzGepngJ", 
            "ExpireTime": "gHtSroIX", 
            "CName": "OMNcUHBi", 
            "TaskSet": [
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 3
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 6
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 5
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 4
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 9
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 4
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 9
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 4
                }
            ], 
            "UGAAId": "dZzFXvcI", 
            "IPList": [
                "LTDhCEfR", 
                "dqrGCTTr", 
                "WeSTnhId", 
                "JYTIXUCM", 
                "tVKrmssT", 
                "jPzPgjnH", 
                "pRTgTntL", 
                "kbZRgozs", 
                "TMxzvytX", 
                "wQhLYIBb"
            ], 
            "CreateTime": "DWsLbYfy"
        }, 
        {
            "UPathSet": [
                {
                    "UPathId": "zGMUDkMM", 
                    "LineFromName": "qzKqgVgq", 
                    "LineToName": "SlpGBgqy", 
                    "UPathName": "TDAgLEZo", 
                    "Bandwidth": "XEnfZdxM", 
                    "LineId": "pceFSQiU"
                }, 
                {
                    "UPathId": "TXhRcMUP", 
                    "LineFromName": "yUzrkanP", 
                    "LineToName": "hoKoShbw", 
                    "UPathName": "mHeoakyv", 
                    "Bandwidth": "yZuiYPQt", 
                    "LineId": "OMqhQwuK"
                }, 
                {
                    "UPathId": "BgocExzM", 
                    "LineFromName": "wIEyAuiG", 
                    "LineToName": "xVfYmWxM", 
                    "UPathName": "UTspWTAS", 
                    "Bandwidth": "WPsNPoXb", 
                    "LineId": "BNUFwDVo"
                }, 
                {
                    "UPathId": "BpQnMLZL", 
                    "LineFromName": "lEjFKHPV", 
                    "LineToName": "QQVRhUAe", 
                    "UPathName": "KqPAVsYk", 
                    "Bandwidth": "dXWlGjmW", 
                    "LineId": "AWhMykpd"
                }, 
                {
                    "UPathId": "oiIUggVi", 
                    "LineFromName": "xYXswWYr", 
                    "LineToName": "htMwtmwQ", 
                    "UPathName": "GWPveZvp", 
                    "Bandwidth": "DcuTGwDa", 
                    "LineId": "OnmFtBap"
                }, 
                {
                    "UPathId": "hByapuRq", 
                    "LineFromName": "tprAkJBv", 
                    "LineToName": "IjPLavNX", 
                    "UPathName": "rrSHlXHs", 
                    "Bandwidth": "rFruJUUO", 
                    "LineId": "QstlJCYh"
                }, 
                {
                    "UPathId": "ahAXURKu", 
                    "LineFromName": "pOsBHqgF", 
                    "LineToName": "BtfYuOhe", 
                    "UPathName": "KTCGFmnp", 
                    "Bandwidth": "KQyJzgPM", 
                    "LineId": "bjVFIAHY"
                }, 
                {
                    "UPathId": "czXJmTuA", 
                    "LineFromName": "OGQauhEr", 
                    "LineToName": "XNRUWIit", 
                    "UPathName": "OAFHzzWA", 
                    "Bandwidth": "wmwygrrh", 
                    "LineId": "dIrESFgM"
                }, 
                {
                    "UPathId": "NeLoqZQq", 
                    "LineFromName": "FeJLmfTw", 
                    "LineToName": "mEzAAsev", 
                    "UPathName": "MiQxzkCG", 
                    "Bandwidth": "LObEPRsa", 
                    "LineId": "YKBxqJkI"
                }, 
                {
                    "UPathId": "ceaOfGfI", 
                    "LineFromName": "boBoicbs", 
                    "LineToName": "fQaaHxwc", 
                    "UPathName": "DsxQwQQk", 
                    "Bandwidth": "LzgpDsnA", 
                    "LineId": "tEHNWXCx"
                }
            ], 
            "Domain": "PZdPCwad", 
            "ChargeType": "lvHTxBmZ", 
            "UGAAName": "VvwtPonn", 
            "ExpireTime": "lFKbUBnL", 
            "CName": "Vksahvhx", 
            "TaskSet": [
                {
                    "Protocol": "TCP", 
                    "Port": 8
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 3
                }
            ], 
            "UGAAId": "LLoOmAtO", 
            "IPList": [
                "usgdMqmZ", 
                "FpzmBAtm", 
                "pjDCOMfv", 
                "mAKBhwBZ", 
                "dhDfBqBw", 
                "deMoPxhl"
            ], 
            "CreateTime": "OMnDBIkG"
        }, 
        {
            "UPathSet": [
                {
                    "UPathId": "lEBUrZWg", 
                    "LineFromName": "kzXvZdbQ", 
                    "LineToName": "JZKDKgWI", 
                    "UPathName": "cjEJUdHD", 
                    "Bandwidth": "smaERNcU", 
                    "LineId": "ttDNpiti"
                }, 
                {
                    "UPathId": "nMywdyNo", 
                    "LineFromName": "RvLSjQac", 
                    "LineToName": "UbBboTHM", 
                    "UPathName": "rzyvvDrV", 
                    "Bandwidth": "gPDSUrwA", 
                    "LineId": "aqrVzYcd"
                }, 
                {
                    "UPathId": "wsOvKZQS", 
                    "LineFromName": "jLkABpxK", 
                    "LineToName": "lrbyVvfn", 
                    "UPathName": "psVrQzTN", 
                    "Bandwidth": "wkzcgTNq", 
                    "LineId": "wrDWXRaH"
                }, 
                {
                    "UPathId": "azemAZFG", 
                    "LineFromName": "kYClWVbq", 
                    "LineToName": "rrhHaDkS", 
                    "UPathName": "CFPLSMZL", 
                    "Bandwidth": "JFsMGEmz", 
                    "LineId": "YHnzpFbD"
                }, 
                {
                    "UPathId": "YKUzoMqz", 
                    "LineFromName": "vUXyHdld", 
                    "LineToName": "LyhPwsWq", 
                    "UPathName": "QBHIFKaG", 
                    "Bandwidth": "eVimjIzd", 
                    "LineId": "syyauPKT"
                }
            ], 
            "Domain": "xuUCwyJg", 
            "ChargeType": "eIWpDXCZ", 
            "UGAAName": "AaXSrlQi", 
            "ExpireTime": "eVAXTdCt", 
            "CName": "opwlHQrf", 
            "TaskSet": [
                {
                    "Protocol": "TCP", 
                    "Port": 1
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 1
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 2
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 5
                }
            ], 
            "UGAAId": "jydDQYxV", 
            "IPList": [
                "xbONuqte", 
                "JnXniujc", 
                "GnmmkYqf", 
                "iCGmWibT", 
                "dlwljDet", 
                "FLMusemw", 
                "PBkUUBYz", 
                "TYZQBbvD", 
                "jHhtGzdQ"
            ], 
            "CreateTime": "QGBzseWr"
        }, 
        {
            "UPathSet": [
                {
                    "UPathId": "ASPRTMEK", 
                    "LineFromName": "qajaTXYr", 
                    "LineToName": "sAUIFgZt", 
                    "UPathName": "tdWmhHQM", 
                    "Bandwidth": "WZELAuvc", 
                    "LineId": "IeTEjynG"
                }, 
                {
                    "UPathId": "WWGjLZsQ", 
                    "LineFromName": "HLwDonKQ", 
                    "LineToName": "PwtrQCdS", 
                    "UPathName": "FwivmLXU", 
                    "Bandwidth": "fZUelWcN", 
                    "LineId": "nmLpdqav"
                }, 
                {
                    "UPathId": "ukWqWUeS", 
                    "LineFromName": "tigKWbpc", 
                    "LineToName": "uwPeLsZO", 
                    "UPathName": "SfwRssMx", 
                    "Bandwidth": "EOjPPiHM", 
                    "LineId": "QjhZKGxj"
                }, 
                {
                    "UPathId": "pXCHiLjI", 
                    "LineFromName": "ySVNnuMe", 
                    "LineToName": "TNUpOkTE", 
                    "UPathName": "jqKPGEdF", 
                    "Bandwidth": "mtnGaFbZ", 
                    "LineId": "ZhkSpTrx"
                }, 
                {
                    "UPathId": "QviljdGI", 
                    "LineFromName": "PGaINUcl", 
                    "LineToName": "ciJUAwuk", 
                    "UPathName": "MZTtuYXG", 
                    "Bandwidth": "omOKyIxq", 
                    "LineId": "kaDkOBZc"
                }, 
                {
                    "UPathId": "ExVDhmfs", 
                    "LineFromName": "jNwoGvvD", 
                    "LineToName": "PkUwVRIA", 
                    "UPathName": "zLGIXtbT", 
                    "Bandwidth": "lNxxLixA", 
                    "LineId": "WsrKQCQA"
                }, 
                {
                    "UPathId": "COLmcqLm", 
                    "LineFromName": "BdOOWUPU", 
                    "LineToName": "gITAaCQh", 
                    "UPathName": "hIRnmgCT", 
                    "Bandwidth": "bLBvrrQA", 
                    "LineId": "rfuVUhXY"
                }, 
                {
                    "UPathId": "ApohXTWG", 
                    "LineFromName": "PwLLBmEW", 
                    "LineToName": "SFivwGGl", 
                    "UPathName": "gjXLuLlg", 
                    "Bandwidth": "XwKVIwHW", 
                    "LineId": "LGuSGNSA"
                }, 
                {
                    "UPathId": "XjceNvyo", 
                    "LineFromName": "axufsgAU", 
                    "LineToName": "tQaNqFYf", 
                    "UPathName": "DyikThEE", 
                    "Bandwidth": "XQQNXIlJ", 
                    "LineId": "RqnaGAfv"
                }, 
                {
                    "UPathId": "BHPTiNAk", 
                    "LineFromName": "gBMOCBuL", 
                    "LineToName": "AOnjZPCV", 
                    "UPathName": "SEymPyeu", 
                    "Bandwidth": "YBZJjmZm", 
                    "LineId": "RiEaTrHC"
                }
            ], 
            "Domain": "IsrxwtDO", 
            "ChargeType": "rdnFkXlj", 
            "UGAAName": "aMQpgtmJ", 
            "ExpireTime": "LZWLTLCw", 
            "CName": "NQLJjKcf", 
            "TaskSet": [
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 1
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 7
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 8
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 4
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 6
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 3
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 4
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 2
                }, 
                {
                    "Protocol": "TCP", 
                    "Port": 3
                }
            ], 
            "UGAAId": "hihrFOpe", 
            "IPList": [
                "LfgIEdgP", 
                "GXcNLcaM", 
                "mMtpHVET", 
                "vFsSpqIe"
            ], 
            "CreateTime": "zjaeWTTn"
        }
    ]
}
```

