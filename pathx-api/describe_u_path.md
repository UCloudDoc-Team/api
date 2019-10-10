# 获取加速线路信息-DescribeUPath

获取加速线路信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UPathId|string|不填 返回所填项目下所有的线路资源，填写则返回一个线路实例|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UPathSet|array|线路信息数组|**Yes**|

## UPathInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|计费模式，默认为Month 按月收费,可选范围['Month','Year','Dynamic']|No|
|Name|string|UPath实例名字|No|
|UPathId|string|UPath加速线路实例ID|No|
|Bandwidth|int|带宽，单位Mbps|No|
|LineId|string|选择的线路|No|
|UGAList|array|与该UPath绑定的UGA列表|No|
|CreateTime|int|UPath创建的时间，10位时间戳|No|
|ExpireTime|int|UPath的过期时间，10位时间戳|No|
|LineFromName|string|线路入口名称|No|
|LineToName|string|线路出口名称|No|
|OutPublicIpList|array|线路出口IP数组|No|

## PathXUGAInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UGAId|string|加速配置ID|No|
|IPList|array|源站IP列表，多个值由半角英文逗号相隔|No|
|Domain|string|源站域名|No|

## OutPublicIpInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IP|string| 线路出口EIP|No|
|Area|string|线路出口机房代号|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUPath
&UPathId=TUbrKTPq
```

# Response Example
```
{
    "UPathSet": [
        {
            "UPathId": "dtCdoIix", 
            "Bandwidth": "fMsZxyoM", 
            "LineId": "rOjKfpjD", 
            "Name": "RqZYbnwD", 
            "UGAAList": [
                {
                    "Status": "Available", 
                    "Domain": "zuzgvRiB", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }
                    ], 
                    "UGAAName": "ZmhaWVHp", 
                    "LineSet": [
                        {
                            "LineFromName": "nxbFhhQs", 
                            "Bandwidth": 2, 
                            "LineToName": "lKGTtSuK", 
                            "LineFrom": "rUWTovSG", 
                            "LineTo": "EnsQmyRD", 
                            "LineId": "IGPgsEpp"
                        }, 
                        {
                            "LineFromName": "HlPZpPeM", 
                            "Bandwidth": 6, 
                            "LineToName": "vmSjcsRM", 
                            "LineFrom": "xAMphkXm", 
                            "LineTo": "UvewSUkd", 
                            "LineId": "AEfHOeMA"
                        }, 
                        {
                            "LineFromName": "WssKRjYj", 
                            "Bandwidth": 1, 
                            "LineToName": "jaoRVXCX", 
                            "LineFrom": "piwGqkpT", 
                            "LineTo": "dIslgLIX", 
                            "LineId": "UKZzXmpa"
                        }, 
                        {
                            "LineFromName": "hgBKkuTk", 
                            "Bandwidth": 5, 
                            "LineToName": "TdaMpbbr", 
                            "LineFrom": "UHGEbidN", 
                            "LineTo": "SdhBmfGx", 
                            "LineId": "MRuWKYap"
                        }, 
                        {
                            "LineFromName": "xVLBPIKR", 
                            "Bandwidth": 9, 
                            "LineToName": "ittzUGrO", 
                            "LineFrom": "hgkwiaNS", 
                            "LineTo": "VhdYNSEs", 
                            "LineId": "woDWYbYj"
                        }, 
                        {
                            "LineFromName": "oAqjQbeG", 
                            "Bandwidth": 7, 
                            "LineToName": "tOgIEmcH", 
                            "LineFrom": "AKohjVKb", 
                            "LineTo": "oxFmrxvp", 
                            "LineId": "yeBQImxg"
                        }
                    ], 
                    "ExpireTime": 9, 
                    "CName": "jSKwfagD", 
                    "ChargeType": "Year", 
                    "UGAAId": "dVrQHJAh", 
                    "IPList": [
                        "OZZPpSOu", 
                        "OQGenhLv", 
                        "ZNtLWXZQ"
                    ], 
                    "CreateTime": 7
                }, 
                {
                    "Status": "Available", 
                    "Domain": "pDEiBWwX", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }
                    ], 
                    "UGAAName": "nvepfRQo", 
                    "LineSet": [
                        {
                            "LineFromName": "KrOFrQKh", 
                            "Bandwidth": 8, 
                            "LineToName": "RXFppvRY", 
                            "LineFrom": "PudHBapx", 
                            "LineTo": "gBKwmuWa", 
                            "LineId": "xrKdYglG"
                        }, 
                        {
                            "LineFromName": "hNoPRjDH", 
                            "Bandwidth": 6, 
                            "LineToName": "xbzrtYrF", 
                            "LineFrom": "PUZytIpf", 
                            "LineTo": "xKHLNNJY", 
                            "LineId": "DJxKpmOc"
                        }, 
                        {
                            "LineFromName": "xSMQsHeD", 
                            "Bandwidth": 8, 
                            "LineToName": "lIgiRNfd", 
                            "LineFrom": "HqHtoWuu", 
                            "LineTo": "XzwCLoIK", 
                            "LineId": "cBnOScUR"
                        }, 
                        {
                            "LineFromName": "cKOwSDtL", 
                            "Bandwidth": 1, 
                            "LineToName": "jpyHYDYH", 
                            "LineFrom": "nmmKxGaW", 
                            "LineTo": "BUczNxUg", 
                            "LineId": "VBoFzmac"
                        }, 
                        {
                            "LineFromName": "HWgTDYcg", 
                            "Bandwidth": 7, 
                            "LineToName": "xpvRPfWa", 
                            "LineFrom": "QuwWYaCB", 
                            "LineTo": "wIILIRpg", 
                            "LineId": "lTqOGoUe"
                        }, 
                        {
                            "LineFromName": "bGywzVmk", 
                            "Bandwidth": 3, 
                            "LineToName": "bTjvrGIg", 
                            "LineFrom": "faTJoReB", 
                            "LineTo": "AJWMcoeV", 
                            "LineId": "KLCJgbKq"
                        }, 
                        {
                            "LineFromName": "BaiQLQdk", 
                            "Bandwidth": 9, 
                            "LineToName": "UNdIhFOC", 
                            "LineFrom": "zgWRVbLc", 
                            "LineTo": "hFdRQqrL", 
                            "LineId": "mImUwKbL"
                        }
                    ], 
                    "ExpireTime": 5, 
                    "CName": "ImjkQljI", 
                    "ChargeType": "Year", 
                    "UGAAId": "FekdUaeL", 
                    "IPList": [
                        "CatfwtXc", 
                        "hJApaPIb", 
                        "uTvdxiuf"
                    ], 
                    "CreateTime": 6
                }, 
                {
                    "Status": "Available", 
                    "Domain": "IGtfcgOv", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }
                    ], 
                    "UGAAName": "nwCIjuyQ", 
                    "LineSet": [
                        {
                            "LineFromName": "OqCmlEkR", 
                            "Bandwidth": 6, 
                            "LineToName": "COdOGUMD", 
                            "LineFrom": "egrWIwQN", 
                            "LineTo": "SuAZzRYJ", 
                            "LineId": "zvQAMxGB"
                        }, 
                        {
                            "LineFromName": "WhUWGfus", 
                            "Bandwidth": 3, 
                            "LineToName": "pcyaAasx", 
                            "LineFrom": "RMFCGyhX", 
                            "LineTo": "HXvDXnfh", 
                            "LineId": "KdENyIEN"
                        }
                    ], 
                    "ExpireTime": 1, 
                    "CName": "RtkbYomJ", 
                    "ChargeType": "Year", 
                    "UGAAId": "eHdDdvbe", 
                    "IPList": [
                        "iwPiRmOi", 
                        "UZblaGos", 
                        "bESwUbZa", 
                        "vjCqNCcq", 
                        "xjvfQTgn", 
                        "xUePvmNc", 
                        "EUYjXmNz", 
                        "nbUNozsH", 
                        "TSCiqzGI"
                    ], 
                    "CreateTime": 1
                }, 
                {
                    "Status": "Available", 
                    "Domain": "ttWMDZFa", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }
                    ], 
                    "UGAAName": "veaSRbcZ", 
                    "LineSet": [
                        {
                            "LineFromName": "jCIdZHvn", 
                            "Bandwidth": 4, 
                            "LineToName": "uMpkgota", 
                            "LineFrom": "IeuTnFRc", 
                            "LineTo": "FNyYYKLO", 
                            "LineId": "cWnywmAJ"
                        }, 
                        {
                            "LineFromName": "OINaFWNY", 
                            "Bandwidth": 4, 
                            "LineToName": "CXJtQKBB", 
                            "LineFrom": "GRvINvFI", 
                            "LineTo": "gSzuVxOE", 
                            "LineId": "BSRxhjNc"
                        }, 
                        {
                            "LineFromName": "KUqMGDfU", 
                            "Bandwidth": 1, 
                            "LineToName": "uZsyDCYQ", 
                            "LineFrom": "kQGVmsdo", 
                            "LineTo": "OoMDKVtp", 
                            "LineId": "OdDFQSGQ"
                        }, 
                        {
                            "LineFromName": "ovMkArmH", 
                            "Bandwidth": 2, 
                            "LineToName": "KHDoQopZ", 
                            "LineFrom": "trYtoJjs", 
                            "LineTo": "dAFcdEgA", 
                            "LineId": "rMHFONxg"
                        }, 
                        {
                            "LineFromName": "oXDQQsCg", 
                            "Bandwidth": 7, 
                            "LineToName": "PEVClefl", 
                            "LineFrom": "HVyUADQb", 
                            "LineTo": "fJeqpawI", 
                            "LineId": "hnVeOGAA"
                        }, 
                        {
                            "LineFromName": "LAqrqqMU", 
                            "Bandwidth": 9, 
                            "LineToName": "tDZrmhre", 
                            "LineFrom": "xPZyiWyG", 
                            "LineTo": "qbAUDUDo", 
                            "LineId": "whVizqbk"
                        }, 
                        {
                            "LineFromName": "KrmHQxLQ", 
                            "Bandwidth": 6, 
                            "LineToName": "zRwzCnUj", 
                            "LineFrom": "rSWBpImL", 
                            "LineTo": "EMvkZDRj", 
                            "LineId": "YWcZoMBo"
                        }, 
                        {
                            "LineFromName": "XRSlRPuE", 
                            "Bandwidth": 9, 
                            "LineToName": "tjrjOZtn", 
                            "LineFrom": "vJfxPuhy", 
                            "LineTo": "KGJVpoHI", 
                            "LineId": "VzzrrcZq"
                        }
                    ], 
                    "ExpireTime": 7, 
                    "CName": "KcznCdkZ", 
                    "ChargeType": "Year", 
                    "UGAAId": "xAVlvarS", 
                    "IPList": [
                        "NkwvgYoH", 
                        "xkeoCcwF", 
                        "pscbjQua", 
                        "wHjBGIZi", 
                        "XdqFygEK", 
                        "ZLyvmbdc", 
                        "NfWOGmbR", 
                        "vzfWXqBJ", 
                        "ozJcovyp"
                    ], 
                    "CreateTime": 7
                }, 
                {
                    "Status": "Available", 
                    "Domain": "VHPZlBKL", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }
                    ], 
                    "UGAAName": "jnhlyhkW", 
                    "LineSet": [
                        {
                            "LineFromName": "qAjqMoOA", 
                            "Bandwidth": 8, 
                            "LineToName": "pZmVSKfy", 
                            "LineFrom": "wrhbwVIk", 
                            "LineTo": "piEGZLuU", 
                            "LineId": "WrDzxFvL"
                        }, 
                        {
                            "LineFromName": "traKIgOi", 
                            "Bandwidth": 8, 
                            "LineToName": "QZyvajDj", 
                            "LineFrom": "rxsUawMt", 
                            "LineTo": "GgkbsIVJ", 
                            "LineId": "mFhvfLFj"
                        }
                    ], 
                    "ExpireTime": 1, 
                    "CName": "wLmuNICC", 
                    "ChargeType": "Year", 
                    "UGAAId": "mNXiUuQz", 
                    "IPList": [
                        "xeaXvuNz", 
                        "KIYTxVSd", 
                        "oRMdthIp", 
                        "ixcTSXCd", 
                        "DkoMuZyl", 
                        "uOrqnInY", 
                        "hxfWVDyP", 
                        "WxQqyTBK", 
                        "QORQzOYx", 
                        "vtDdOPyp"
                    ], 
                    "CreateTime": 9
                }, 
                {
                    "Status": "Available", 
                    "Domain": "kqEcrGtK", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }
                    ], 
                    "UGAAName": "DfIgqDEJ", 
                    "LineSet": [
                        {
                            "LineFromName": "RtIUJHeX", 
                            "Bandwidth": 7, 
                            "LineToName": "swkmFnpV", 
                            "LineFrom": "LJxdveLl", 
                            "LineTo": "fgixCiNG", 
                            "LineId": "KKsUoFiF"
                        }, 
                        {
                            "LineFromName": "MbiDfsES", 
                            "Bandwidth": 1, 
                            "LineToName": "SdBcGWkR", 
                            "LineFrom": "pGoAPAEW", 
                            "LineTo": "IrlAUhFL", 
                            "LineId": "JcuhtwTz"
                        }, 
                        {
                            "LineFromName": "BYVhTZSD", 
                            "Bandwidth": 1, 
                            "LineToName": "tpXMfzCr", 
                            "LineFrom": "dDytXbmg", 
                            "LineTo": "yslNioMF", 
                            "LineId": "paEFgTyh"
                        }, 
                        {
                            "LineFromName": "xvjNSydF", 
                            "Bandwidth": 3, 
                            "LineToName": "segwTHPw", 
                            "LineFrom": "YpVwXTaU", 
                            "LineTo": "EWUPBLVL", 
                            "LineId": "UbggiAhE"
                        }, 
                        {
                            "LineFromName": "yjMOjxpR", 
                            "Bandwidth": 1, 
                            "LineToName": "ZXtfyEfD", 
                            "LineFrom": "ySjtGoFl", 
                            "LineTo": "HeJLfGcf", 
                            "LineId": "IBDXmWHf"
                        }, 
                        {
                            "LineFromName": "lCSnPMeW", 
                            "Bandwidth": 5, 
                            "LineToName": "PWueiqRM", 
                            "LineFrom": "RQKuLehz", 
                            "LineTo": "nKxLuYWM", 
                            "LineId": "hkHJdnbk"
                        }, 
                        {
                            "LineFromName": "nuQGlznC", 
                            "Bandwidth": 1, 
                            "LineToName": "zjRCyarj", 
                            "LineFrom": "ocMAxoqV", 
                            "LineTo": "ZRgsLKAw", 
                            "LineId": "MtqwqePg"
                        }, 
                        {
                            "LineFromName": "xnwFgSXm", 
                            "Bandwidth": 9, 
                            "LineToName": "qqTiobPf", 
                            "LineFrom": "oYROsDpK", 
                            "LineTo": "jRfXoOkZ", 
                            "LineId": "nPZpYlAF"
                        }, 
                        {
                            "LineFromName": "sOjNzTEe", 
                            "Bandwidth": 9, 
                            "LineToName": "bxWckoIl", 
                            "LineFrom": "rEqYNyPn", 
                            "LineTo": "FXYDpbiJ", 
                            "LineId": "GWwWxghL"
                        }, 
                        {
                            "LineFromName": "nrLFiJCV", 
                            "Bandwidth": 3, 
                            "LineToName": "XGIMJMug", 
                            "LineFrom": "lqLkLLRd", 
                            "LineTo": "wUdeUtNs", 
                            "LineId": "iUuAApUk"
                        }
                    ], 
                    "ExpireTime": 6, 
                    "CName": "lzghPHdy", 
                    "ChargeType": "Year", 
                    "UGAAId": "NKaHEsIh", 
                    "IPList": [
                        "WRlxNVOx", 
                        "pZiNlNLR", 
                        "bbqmZljI"
                    ], 
                    "CreateTime": 7
                }
            ]
        }, 
        {
            "UPathId": "FjfAoppr", 
            "Bandwidth": "buVZNaJI", 
            "LineId": "lqYoeyha", 
            "Name": "RPbvscGH", 
            "UGAAList": [
                {
                    "Status": "Available", 
                    "Domain": "cUyuOGKH", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }
                    ], 
                    "UGAAName": "QuaAjoCm", 
                    "LineSet": [
                        {
                            "LineFromName": "NANrBboX", 
                            "Bandwidth": 5, 
                            "LineToName": "pxdlfPIn", 
                            "LineFrom": "NNYXOgGg", 
                            "LineTo": "dhDmoiWQ", 
                            "LineId": "BHESecNq"
                        }, 
                        {
                            "LineFromName": "uWPBnSby", 
                            "Bandwidth": 9, 
                            "LineToName": "saAnPQCA", 
                            "LineFrom": "VotXzGni", 
                            "LineTo": "UYdeNsMx", 
                            "LineId": "uDNqdoKb"
                        }, 
                        {
                            "LineFromName": "zOdsIAzu", 
                            "Bandwidth": 2, 
                            "LineToName": "lIhEvcMv", 
                            "LineFrom": "gvnsTCLJ", 
                            "LineTo": "XBURmLBL", 
                            "LineId": "tiZsmEbd"
                        }, 
                        {
                            "LineFromName": "LFFaOZcm", 
                            "Bandwidth": 5, 
                            "LineToName": "JkNukLUD", 
                            "LineFrom": "ZWvWuaUD", 
                            "LineTo": "seYJOMiN", 
                            "LineId": "tvbiQdgH"
                        }, 
                        {
                            "LineFromName": "undJiMvm", 
                            "Bandwidth": 8, 
                            "LineToName": "TpWjjnoa", 
                            "LineFrom": "KMNYPpuZ", 
                            "LineTo": "yOkZEbiA", 
                            "LineId": "McjyDCJj"
                        }, 
                        {
                            "LineFromName": "ChufArDH", 
                            "Bandwidth": 2, 
                            "LineToName": "xoVGhLUu", 
                            "LineFrom": "iUTBCJLT", 
                            "LineTo": "CNXBpGHR", 
                            "LineId": "mooMysfX"
                        }, 
                        {
                            "LineFromName": "LMlHFWGP", 
                            "Bandwidth": 9, 
                            "LineToName": "LrPrnmAT", 
                            "LineFrom": "SIAghlcH", 
                            "LineTo": "BmjeLFhO", 
                            "LineId": "mTkFSdmJ"
                        }, 
                        {
                            "LineFromName": "hkLxOdsL", 
                            "Bandwidth": 7, 
                            "LineToName": "UIDihfUl", 
                            "LineFrom": "LKPWCtRx", 
                            "LineTo": "NlPCrrnA", 
                            "LineId": "bONEGVWi"
                        }, 
                        {
                            "LineFromName": "tIMCEaZT", 
                            "Bandwidth": 1, 
                            "LineToName": "ZzNtEsog", 
                            "LineFrom": "GVZIwkkb", 
                            "LineTo": "NiJjZSun", 
                            "LineId": "CYldfQYB"
                        }
                    ], 
                    "ExpireTime": 1, 
                    "CName": "IbPpVqjx", 
                    "ChargeType": "Year", 
                    "UGAAId": "STMDmaSO", 
                    "IPList": [
                        "DjiTiwyO", 
                        "gZPMSOEm", 
                        "XFTxoIpL"
                    ], 
                    "CreateTime": 6
                }, 
                {
                    "Status": "Available", 
                    "Domain": "SuBtphkp", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }
                    ], 
                    "UGAAName": "KbhdwzHr", 
                    "LineSet": [
                        {
                            "LineFromName": "sFdBYEVQ", 
                            "Bandwidth": 9, 
                            "LineToName": "aOqrQzIU", 
                            "LineFrom": "ItnzqZUX", 
                            "LineTo": "CMgsZgpU", 
                            "LineId": "GvSFjntF"
                        }, 
                        {
                            "LineFromName": "FYaOFIGQ", 
                            "Bandwidth": 2, 
                            "LineToName": "zinWLDth", 
                            "LineFrom": "SCvLtLSY", 
                            "LineTo": "ZpLjuHIc", 
                            "LineId": "HmJiuTPW"
                        }, 
                        {
                            "LineFromName": "JDRqrCGW", 
                            "Bandwidth": 6, 
                            "LineToName": "uJvyDHql", 
                            "LineFrom": "OFihqRHI", 
                            "LineTo": "SQFQuvqD", 
                            "LineId": "ODybQkNX"
                        }, 
                        {
                            "LineFromName": "hTDzvUEB", 
                            "Bandwidth": 2, 
                            "LineToName": "iwOaMdUK", 
                            "LineFrom": "sDkaINAU", 
                            "LineTo": "xwvSRmcQ", 
                            "LineId": "cacUNAcG"
                        }, 
                        {
                            "LineFromName": "gXbtVZfV", 
                            "Bandwidth": 4, 
                            "LineToName": "dHWuZOvg", 
                            "LineFrom": "TKaxRKhe", 
                            "LineTo": "ykLdlYBF", 
                            "LineId": "mFtrLPod"
                        }, 
                        {
                            "LineFromName": "azWnAZRC", 
                            "Bandwidth": 1, 
                            "LineToName": "LTlNbNxE", 
                            "LineFrom": "KulOTWhm", 
                            "LineTo": "NipSbNeJ", 
                            "LineId": "rackTDNL"
                        }, 
                        {
                            "LineFromName": "bemKGwcb", 
                            "Bandwidth": 8, 
                            "LineToName": "IrkkXdjf", 
                            "LineFrom": "NWnfbuhN", 
                            "LineTo": "lsfocmFQ", 
                            "LineId": "XEdEBmNX"
                        }, 
                        {
                            "LineFromName": "KaXikwhT", 
                            "Bandwidth": 7, 
                            "LineToName": "cWgTxtTN", 
                            "LineFrom": "eDnWhjJa", 
                            "LineTo": "wodBQjxs", 
                            "LineId": "GOkezxie"
                        }
                    ], 
                    "ExpireTime": 4, 
                    "CName": "eAlZwSNv", 
                    "ChargeType": "Year", 
                    "UGAAId": "DxnhFrrm", 
                    "IPList": [
                        "mfYxNijJ", 
                        "YOtryZWL", 
                        "uxqXkbUx", 
                        "bimVMSnc", 
                        "qsLTCOIG", 
                        "pMOzbBbD", 
                        "CpUsWhob"
                    ], 
                    "CreateTime": 7
                }, 
                {
                    "Status": "Available", 
                    "Domain": "tKpiKSTA", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }
                    ], 
                    "UGAAName": "wnWKGIVG", 
                    "LineSet": [
                        {
                            "LineFromName": "dMzVGZgW", 
                            "Bandwidth": 7, 
                            "LineToName": "DOybPpMM", 
                            "LineFrom": "gmDKRlni", 
                            "LineTo": "JgdaccZi", 
                            "LineId": "LiIoGYUl"
                        }, 
                        {
                            "LineFromName": "RdzvoEKX", 
                            "Bandwidth": 8, 
                            "LineToName": "PcBREMfo", 
                            "LineFrom": "peLeaLDS", 
                            "LineTo": "UzCdLcCZ", 
                            "LineId": "WLFXTEDU"
                        }
                    ], 
                    "ExpireTime": 9, 
                    "CName": "TGAcdMLO", 
                    "ChargeType": "Year", 
                    "UGAAId": "BmVCeMah", 
                    "IPList": [
                        "MRaOFfUD", 
                        "mAFCqfmG", 
                        "pfIdlkxb", 
                        "GnLTBzny", 
                        "MJctppOq", 
                        "fjquXjxJ", 
                        "dsVTiEip", 
                        "nWKSoABx", 
                        "bbWpgLTy", 
                        "hfIWaGSQ"
                    ], 
                    "CreateTime": 2
                }, 
                {
                    "Status": "Available", 
                    "Domain": "JZkYLhXe", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }
                    ], 
                    "UGAAName": "fXoLHIHr", 
                    "LineSet": [
                        {
                            "LineFromName": "BWQQVjjX", 
                            "Bandwidth": 7, 
                            "LineToName": "IcoJkcnU", 
                            "LineFrom": "LfXGpOcp", 
                            "LineTo": "GqMJTnDA", 
                            "LineId": "KiVoJImn"
                        }, 
                        {
                            "LineFromName": "eFtpvkUp", 
                            "Bandwidth": 4, 
                            "LineToName": "yTYzufKU", 
                            "LineFrom": "XeapXlJR", 
                            "LineTo": "fEPEXhjU", 
                            "LineId": "qyvtzcIr"
                        }
                    ], 
                    "ExpireTime": 6, 
                    "CName": "hNnNRRlE", 
                    "ChargeType": "Year", 
                    "UGAAId": "huStKUuQ", 
                    "IPList": [
                        "VFmcZQoA", 
                        "PjYtIxDX", 
                        "ZdXjCSSg", 
                        "bdUQHtYy", 
                        "pwUiVKRs", 
                        "vFVGHjhK", 
                        "cqoZDHiE"
                    ], 
                    "CreateTime": 3
                }, 
                {
                    "Status": "Available", 
                    "Domain": "rPossUxY", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }
                    ], 
                    "UGAAName": "GgWyFnkQ", 
                    "LineSet": [
                        {
                            "LineFromName": "OVacsiUs", 
                            "Bandwidth": 8, 
                            "LineToName": "iDaivfWP", 
                            "LineFrom": "tDPzPIdW", 
                            "LineTo": "QxRAuKLd", 
                            "LineId": "IoHyEMTc"
                        }, 
                        {
                            "LineFromName": "bcStzYvg", 
                            "Bandwidth": 1, 
                            "LineToName": "hvqsLsaQ", 
                            "LineFrom": "GkcrCvIH", 
                            "LineTo": "eLEBAHHM", 
                            "LineId": "cLeUxvZE"
                        }, 
                        {
                            "LineFromName": "HxvmSjoN", 
                            "Bandwidth": 1, 
                            "LineToName": "VHTapsEb", 
                            "LineFrom": "TkTQYntP", 
                            "LineTo": "dEuzDXbb", 
                            "LineId": "qLAvNwXI"
                        }, 
                        {
                            "LineFromName": "yFxgZdOw", 
                            "Bandwidth": 6, 
                            "LineToName": "NscxeJjX", 
                            "LineFrom": "CEuIOfNV", 
                            "LineTo": "sTwdvBIq", 
                            "LineId": "clfYgCDC"
                        }, 
                        {
                            "LineFromName": "OACswNkR", 
                            "Bandwidth": 2, 
                            "LineToName": "YRSNzzDq", 
                            "LineFrom": "BIRBVHhK", 
                            "LineTo": "axoBwtCz", 
                            "LineId": "aZXfSQvd"
                        }, 
                        {
                            "LineFromName": "pfWbULri", 
                            "Bandwidth": 7, 
                            "LineToName": "BwpPBFsr", 
                            "LineFrom": "eRNYFjCL", 
                            "LineTo": "QIDqIVfm", 
                            "LineId": "ZBmgEAwt"
                        }
                    ], 
                    "ExpireTime": 7, 
                    "CName": "OjOGFIlM", 
                    "ChargeType": "Year", 
                    "UGAAId": "BrjqZiWO", 
                    "IPList": [
                        "tFBFKWGe", 
                        "Dkoqdwhz", 
                        "dvyaAIjb", 
                        "YuqvMfFR", 
                        "Hxxydldh", 
                        "ycqRaJpr", 
                        "ABooPlQC", 
                        "kilQwgIs", 
                        "fqaHNNyg", 
                        "PuERnCxm"
                    ], 
                    "CreateTime": 3
                }, 
                {
                    "Status": "Available", 
                    "Domain": "fRqqeWRT", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }
                    ], 
                    "UGAAName": "MbfZAtSO", 
                    "LineSet": [
                        {
                            "LineFromName": "mlaoDVVP", 
                            "Bandwidth": 9, 
                            "LineToName": "tSqBDYyT", 
                            "LineFrom": "DWIGHdtW", 
                            "LineTo": "HSKdNWma", 
                            "LineId": "LdQYaPuw"
                        }, 
                        {
                            "LineFromName": "BofgITJP", 
                            "Bandwidth": 1, 
                            "LineToName": "YkhmUaau", 
                            "LineFrom": "gPfTbqmc", 
                            "LineTo": "KoSEBFcz", 
                            "LineId": "ayYZulAN"
                        }
                    ], 
                    "ExpireTime": 1, 
                    "CName": "OrOrjDII", 
                    "ChargeType": "Year", 
                    "UGAAId": "sqDkeEQY", 
                    "IPList": [
                        "nSciXPMv", 
                        "gDxSUjCa", 
                        "UuCnmSmL"
                    ], 
                    "CreateTime": 3
                }, 
                {
                    "Status": "Available", 
                    "Domain": "BURNgIus", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }
                    ], 
                    "UGAAName": "YLyLlCbf", 
                    "LineSet": [
                        {
                            "LineFromName": "rrcRmvtN", 
                            "Bandwidth": 3, 
                            "LineToName": "QtxuZnwT", 
                            "LineFrom": "xqWDKqXT", 
                            "LineTo": "iCeXbYEh", 
                            "LineId": "bxRJdEWz"
                        }, 
                        {
                            "LineFromName": "gMbWYZXE", 
                            "Bandwidth": 1, 
                            "LineToName": "JaOwCajS", 
                            "LineFrom": "JCDmvgfK", 
                            "LineTo": "dNjwPQFx", 
                            "LineId": "JZnZIlgB"
                        }, 
                        {
                            "LineFromName": "YFCeysYY", 
                            "Bandwidth": 3, 
                            "LineToName": "vJendCVN", 
                            "LineFrom": "oCDSapdq", 
                            "LineTo": "qRQHrfLv", 
                            "LineId": "qNyLudmA"
                        }, 
                        {
                            "LineFromName": "wsJoMCXq", 
                            "Bandwidth": 1, 
                            "LineToName": "PIsFkduj", 
                            "LineFrom": "kjJuUdSQ", 
                            "LineTo": "kbRbLrsC", 
                            "LineId": "kYDJXcsQ"
                        }, 
                        {
                            "LineFromName": "QBWWMrvb", 
                            "Bandwidth": 6, 
                            "LineToName": "ectIBpkF", 
                            "LineFrom": "MTPariyO", 
                            "LineTo": "vzZHwMZq", 
                            "LineId": "wdKLAfAM"
                        }, 
                        {
                            "LineFromName": "TKtbNraj", 
                            "Bandwidth": 6, 
                            "LineToName": "jUKEycHz", 
                            "LineFrom": "pTgliTUR", 
                            "LineTo": "pVQdTpcI", 
                            "LineId": "edRzbihY"
                        }, 
                        {
                            "LineFromName": "WDcnxjcq", 
                            "Bandwidth": 7, 
                            "LineToName": "GLzaWMnm", 
                            "LineFrom": "pyeanXUb", 
                            "LineTo": "iichdxNg", 
                            "LineId": "XBytVpZz"
                        }, 
                        {
                            "LineFromName": "HShlLRxu", 
                            "Bandwidth": 5, 
                            "LineToName": "stuqWeCs", 
                            "LineFrom": "HByawRbb", 
                            "LineTo": "QpjifWXT", 
                            "LineId": "ieBKqFux"
                        }, 
                        {
                            "LineFromName": "oCiqadPM", 
                            "Bandwidth": 9, 
                            "LineToName": "MmKxBSIx", 
                            "LineFrom": "DOkHVrjE", 
                            "LineTo": "bBBWbYrV", 
                            "LineId": "wddgRIGc"
                        }, 
                        {
                            "LineFromName": "wsBeczLq", 
                            "Bandwidth": 7, 
                            "LineToName": "NfRDJioL", 
                            "LineFrom": "nrOfMjIC", 
                            "LineTo": "hDSdgDKi", 
                            "LineId": "fgNweqXj"
                        }
                    ], 
                    "ExpireTime": 8, 
                    "CName": "WKdjrCMa", 
                    "ChargeType": "Year", 
                    "UGAAId": "KAeWjqaq", 
                    "IPList": [
                        "yTXMLdLK", 
                        "qmDlzmAE", 
                        "ZnwbSXsX", 
                        "ETpeQyYs", 
                        "xPUYYDMh", 
                        "TIaQtQqv", 
                        "lkVQhCel", 
                        "wPaTDeAG", 
                        "cWTrZhgU"
                    ], 
                    "CreateTime": 7
                }
            ]
        }, 
        {
            "UPathId": "McYbyVro", 
            "Bandwidth": "bTVrwNiu", 
            "LineId": "TvhQQVUk", 
            "Name": "XetARsft", 
            "UGAAList": [
                {
                    "Status": "Available", 
                    "Domain": "dzLEvzBq", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }
                    ], 
                    "UGAAName": "NXWswrGX", 
                    "LineSet": [
                        {
                            "LineFromName": "yeyclAGJ", 
                            "Bandwidth": 6, 
                            "LineToName": "CbajEKEX", 
                            "LineFrom": "hjYfWvaz", 
                            "LineTo": "BVJmMswy", 
                            "LineId": "pQzSEtmB"
                        }, 
                        {
                            "LineFromName": "WNrbOKGl", 
                            "Bandwidth": 2, 
                            "LineToName": "rxlmcacG", 
                            "LineFrom": "eQfBTbJh", 
                            "LineTo": "zVNNDcLU", 
                            "LineId": "hPJpOAhR"
                        }, 
                        {
                            "LineFromName": "AXZsommr", 
                            "Bandwidth": 6, 
                            "LineToName": "MFuflGuJ", 
                            "LineFrom": "SqvbMlrS", 
                            "LineTo": "MkyXPSwW", 
                            "LineId": "CLhzSZtC"
                        }, 
                        {
                            "LineFromName": "ecHVpmAF", 
                            "Bandwidth": 3, 
                            "LineToName": "SYjqybgc", 
                            "LineFrom": "TKGdYoSe", 
                            "LineTo": "iYtemJrT", 
                            "LineId": "OOFruTUC"
                        }
                    ], 
                    "ExpireTime": 4, 
                    "CName": "fMCuTmPl", 
                    "ChargeType": "Year", 
                    "UGAAId": "ydKEcBPb", 
                    "IPList": [
                        "VvLpXGJv", 
                        "alowkAcL", 
                        "wJotUstW", 
                        "KBkJpJFm", 
                        "jaKlnosS", 
                        "JOpQrMGO", 
                        "XSvupgRn", 
                        "PBLrjDPH", 
                        "iroEeYie"
                    ], 
                    "CreateTime": 4
                }, 
                {
                    "Status": "Available", 
                    "Domain": "OuMwpeoP", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }
                    ], 
                    "UGAAName": "qdRaLEPJ", 
                    "LineSet": [
                        {
                            "LineFromName": "OIRgXdXY", 
                            "Bandwidth": 4, 
                            "LineToName": "LkSDxPCF", 
                            "LineFrom": "XAHeaVnI", 
                            "LineTo": "SuIEWJNP", 
                            "LineId": "JWTSWSLB"
                        }, 
                        {
                            "LineFromName": "cHsAjuNJ", 
                            "Bandwidth": 6, 
                            "LineToName": "SAfSLwiT", 
                            "LineFrom": "gtmqzpKJ", 
                            "LineTo": "dzsbWwiC", 
                            "LineId": "haaFpAdG"
                        }, 
                        {
                            "LineFromName": "EGQGxmKG", 
                            "Bandwidth": 1, 
                            "LineToName": "HUVYLKJH", 
                            "LineFrom": "wGUFopmE", 
                            "LineTo": "lGHPHIDx", 
                            "LineId": "zrmXyrNO"
                        }
                    ], 
                    "ExpireTime": 3, 
                    "CName": "HoFqzdUu", 
                    "ChargeType": "Year", 
                    "UGAAId": "xbQYtfyv", 
                    "IPList": [
                        "DknhdaIM", 
                        "VwygKlyj", 
                        "KQGSHpNb", 
                        "lfQOOSvZ", 
                        "CMtTNAOX"
                    ], 
                    "CreateTime": 6
                }, 
                {
                    "Status": "Available", 
                    "Domain": "qkeAvRWa", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }
                    ], 
                    "UGAAName": "zBDITNHg", 
                    "LineSet": [
                        {
                            "LineFromName": "MUtXLmeu", 
                            "Bandwidth": 4, 
                            "LineToName": "LnutFDKN", 
                            "LineFrom": "DcxmFuWN", 
                            "LineTo": "AEUDBxXM", 
                            "LineId": "PbLedTTY"
                        }, 
                        {
                            "LineFromName": "hPQMiMiM", 
                            "Bandwidth": 3, 
                            "LineToName": "viRhECYV", 
                            "LineFrom": "wdsrDReT", 
                            "LineTo": "OiwivwqX", 
                            "LineId": "omJUTvzt"
                        }, 
                        {
                            "LineFromName": "IpVWhiUI", 
                            "Bandwidth": 1, 
                            "LineToName": "jRhEuKtb", 
                            "LineFrom": "rGeSPjSU", 
                            "LineTo": "mOfwaFye", 
                            "LineId": "QpLybNrp"
                        }, 
                        {
                            "LineFromName": "QPIZIXnh", 
                            "Bandwidth": 1, 
                            "LineToName": "kJDHnOBB", 
                            "LineFrom": "zSwZTYzB", 
                            "LineTo": "NpCMAeCH", 
                            "LineId": "COoqltaR"
                        }, 
                        {
                            "LineFromName": "fmbKcyGQ", 
                            "Bandwidth": 9, 
                            "LineToName": "hQYEqnDR", 
                            "LineFrom": "VkEekdZK", 
                            "LineTo": "DzLwUbaj", 
                            "LineId": "IgODxkVZ"
                        }, 
                        {
                            "LineFromName": "IKLGTUOh", 
                            "Bandwidth": 9, 
                            "LineToName": "fdYpJszz", 
                            "LineFrom": "sQKzmqjv", 
                            "LineTo": "wgPcvljP", 
                            "LineId": "BmVJjZyG"
                        }, 
                        {
                            "LineFromName": "uRakCAFq", 
                            "Bandwidth": 6, 
                            "LineToName": "yhESBGsc", 
                            "LineFrom": "wDcAZKxY", 
                            "LineTo": "xjwdVRnk", 
                            "LineId": "jXxwpbhG"
                        }, 
                        {
                            "LineFromName": "pGDWhyah", 
                            "Bandwidth": 2, 
                            "LineToName": "IEiIpQMI", 
                            "LineFrom": "djsIxsZQ", 
                            "LineTo": "DNNpHZcR", 
                            "LineId": "yNuVTVIJ"
                        }
                    ], 
                    "ExpireTime": 1, 
                    "CName": "GTdwdMtb", 
                    "ChargeType": "Year", 
                    "UGAAId": "lrcmltNa", 
                    "IPList": [
                        "MOaVyMQb", 
                        "sLYClQQA", 
                        "CtJsWlvF", 
                        "OHSRJXNE", 
                        "JQeVTtBc", 
                        "yPnNwjpM"
                    ], 
                    "CreateTime": 4
                }, 
                {
                    "Status": "Available", 
                    "Domain": "XpFfNYSl", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }
                    ], 
                    "UGAAName": "MBRWEceZ", 
                    "LineSet": [
                        {
                            "LineFromName": "ururauig", 
                            "Bandwidth": 7, 
                            "LineToName": "HxRshjtC", 
                            "LineFrom": "bJvQfrse", 
                            "LineTo": "ytvSSULF", 
                            "LineId": "MaWMCnes"
                        }, 
                        {
                            "LineFromName": "nGJvCcRN", 
                            "Bandwidth": 9, 
                            "LineToName": "wZUMvcEu", 
                            "LineFrom": "IvrbHrcv", 
                            "LineTo": "VsUPylSa", 
                            "LineId": "HSEQtbzJ"
                        }, 
                        {
                            "LineFromName": "HYWQllXT", 
                            "Bandwidth": 6, 
                            "LineToName": "lGCcUawZ", 
                            "LineFrom": "bCLwFzbC", 
                            "LineTo": "QzYcZSWC", 
                            "LineId": "RkhMhwnO"
                        }, 
                        {
                            "LineFromName": "hOvoawxi", 
                            "Bandwidth": 3, 
                            "LineToName": "UydGyFBu", 
                            "LineFrom": "jTwcXLxC", 
                            "LineTo": "kjPcYlwL", 
                            "LineId": "czgTgXlj"
                        }, 
                        {
                            "LineFromName": "EXAtMkjN", 
                            "Bandwidth": 4, 
                            "LineToName": "qMueYdXn", 
                            "LineFrom": "NnvwOgxb", 
                            "LineTo": "bMFIVUDA", 
                            "LineId": "SHtmTwgb"
                        }, 
                        {
                            "LineFromName": "gPSinVvg", 
                            "Bandwidth": 7, 
                            "LineToName": "FBCZdwoY", 
                            "LineFrom": "OMWwCiAT", 
                            "LineTo": "CJnXicaJ", 
                            "LineId": "EzucliWr"
                        }, 
                        {
                            "LineFromName": "wuHdjQFj", 
                            "Bandwidth": 9, 
                            "LineToName": "lwzmJOuy", 
                            "LineFrom": "wwjNwuIU", 
                            "LineTo": "iDwZQCfu", 
                            "LineId": "yvEgYMIp"
                        }
                    ], 
                    "ExpireTime": 8, 
                    "CName": "jyMvfUcd", 
                    "ChargeType": "Year", 
                    "UGAAId": "TOUTCTgP", 
                    "IPList": [
                        "uLRrwbPP", 
                        "BkYcIFsC", 
                        "EmLQtBXW", 
                        "LZIwrmMB", 
                        "iiAkPjEO", 
                        "NVRnqTJS"
                    ], 
                    "CreateTime": 7
                }, 
                {
                    "Status": "Available", 
                    "Domain": "ToKxlHfD", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }
                    ], 
                    "UGAAName": "yaQErsBR", 
                    "LineSet": [
                        {
                            "LineFromName": "aLshdIys", 
                            "Bandwidth": 4, 
                            "LineToName": "iicyHwzp", 
                            "LineFrom": "FkehglNC", 
                            "LineTo": "uMNUQniG", 
                            "LineId": "xTPEUTig"
                        }, 
                        {
                            "LineFromName": "XgKGoVpv", 
                            "Bandwidth": 9, 
                            "LineToName": "GyBAcMfN", 
                            "LineFrom": "AVoFapGb", 
                            "LineTo": "SOJUlWNE", 
                            "LineId": "tXlviBXr"
                        }, 
                        {
                            "LineFromName": "iISubpBv", 
                            "Bandwidth": 4, 
                            "LineToName": "VWPZknTA", 
                            "LineFrom": "CuTTikLm", 
                            "LineTo": "rJsoZUvY", 
                            "LineId": "ktsrRlcX"
                        }
                    ], 
                    "ExpireTime": 1, 
                    "CName": "tyiFEqox", 
                    "ChargeType": "Year", 
                    "UGAAId": "XmsdtCXK", 
                    "IPList": [
                        "xVoAwlud", 
                        "JnpukllW", 
                        "nPWXVKZo", 
                        "NsnqwblZ", 
                        "vddQDhnB", 
                        "bihEiCcl", 
                        "pmghKnQy", 
                        "HFFMpxyW", 
                        "GmNXkQyu", 
                        "qawykOcz"
                    ], 
                    "CreateTime": 5
                }, 
                {
                    "Status": "Available", 
                    "Domain": "UZQFDnvB", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }
                    ], 
                    "UGAAName": "pqmVDBub", 
                    "LineSet": [
                        {
                            "LineFromName": "oIERAkfX", 
                            "Bandwidth": 9, 
                            "LineToName": "WgvItdbm", 
                            "LineFrom": "SmIUtzSZ", 
                            "LineTo": "sNEZUlHm", 
                            "LineId": "jbYtlvrV"
                        }, 
                        {
                            "LineFromName": "RnWnCgUP", 
                            "Bandwidth": 1, 
                            "LineToName": "MVBucjLG", 
                            "LineFrom": "svZKDUps", 
                            "LineTo": "dzigeNvY", 
                            "LineId": "faaoJVWn"
                        }, 
                        {
                            "LineFromName": "SENhJLcx", 
                            "Bandwidth": 3, 
                            "LineToName": "nCDemYya", 
                            "LineFrom": "BUcRDaHE", 
                            "LineTo": "jIZzPcUc", 
                            "LineId": "tIApoAPG"
                        }
                    ], 
                    "ExpireTime": 9, 
                    "CName": "KPbEhsZX", 
                    "ChargeType": "Year", 
                    "UGAAId": "pSMQzNne", 
                    "IPList": [
                        "RiVHQEhA", 
                        "kqOuZRHX", 
                        "mRiJyXjm", 
                        "DHAUrdcc", 
                        "oqqPyNDq", 
                        "fuTmjlIR", 
                        "fZBSsIWj", 
                        "LMseVQnG"
                    ], 
                    "CreateTime": 4
                }, 
                {
                    "Status": "Available", 
                    "Domain": "XHwUvnco", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }
                    ], 
                    "UGAAName": "YGbvIucx", 
                    "LineSet": [
                        {
                            "LineFromName": "bTTDXdMD", 
                            "Bandwidth": 3, 
                            "LineToName": "xRHnZUtB", 
                            "LineFrom": "AVUWfdUS", 
                            "LineTo": "PpDZqGsh", 
                            "LineId": "yyVwkJIm"
                        }, 
                        {
                            "LineFromName": "nIBgicpi", 
                            "Bandwidth": 1, 
                            "LineToName": "UtVFmCTh", 
                            "LineFrom": "DEOfPCGS", 
                            "LineTo": "JTLoGtGX", 
                            "LineId": "AyoYlUnd"
                        }, 
                        {
                            "LineFromName": "CcudkCao", 
                            "Bandwidth": 8, 
                            "LineToName": "FCAAZyvl", 
                            "LineFrom": "GqwQmzqJ", 
                            "LineTo": "CSAFzplc", 
                            "LineId": "AGUAUKGV"
                        }
                    ], 
                    "ExpireTime": 9, 
                    "CName": "hXcivSkc", 
                    "ChargeType": "Year", 
                    "UGAAId": "abPOEngF", 
                    "IPList": [
                        "wfgTDHOM", 
                        "woGMycSA", 
                        "oKUpJtXO", 
                        "dOwJmHOz"
                    ], 
                    "CreateTime": 4
                }, 
                {
                    "Status": "Available", 
                    "Domain": "czcRsAsu", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }
                    ], 
                    "UGAAName": "FaYXRksg", 
                    "LineSet": [
                        {
                            "LineFromName": "wrriRKSF", 
                            "Bandwidth": 5, 
                            "LineToName": "PIiLQxEU", 
                            "LineFrom": "YuXzMWEW", 
                            "LineTo": "URAVZqxk", 
                            "LineId": "kcEqglEQ"
                        }, 
                        {
                            "LineFromName": "EsxqNmZD", 
                            "Bandwidth": 7, 
                            "LineToName": "oCDObXYX", 
                            "LineFrom": "ZUVInMgf", 
                            "LineTo": "sWayNBSO", 
                            "LineId": "abRFAjrr"
                        }, 
                        {
                            "LineFromName": "WboFGGnH", 
                            "Bandwidth": 1, 
                            "LineToName": "NyxMzUkq", 
                            "LineFrom": "JodyOwUW", 
                            "LineTo": "kozwRJYs", 
                            "LineId": "rJMASriL"
                        }, 
                        {
                            "LineFromName": "flgLHAcU", 
                            "Bandwidth": 6, 
                            "LineToName": "pYBlLoGw", 
                            "LineFrom": "PfXIZdHn", 
                            "LineTo": "KhEfhTLF", 
                            "LineId": "XPcuDMSg"
                        }, 
                        {
                            "LineFromName": "uVoBjaRD", 
                            "Bandwidth": 5, 
                            "LineToName": "umzxOsXy", 
                            "LineFrom": "SRnJBbje", 
                            "LineTo": "IhnLvQFl", 
                            "LineId": "iDtYheSe"
                        }, 
                        {
                            "LineFromName": "sPxOGnPU", 
                            "Bandwidth": 6, 
                            "LineToName": "ZyXFPPSi", 
                            "LineFrom": "fRpnelTC", 
                            "LineTo": "nHuFrMAP", 
                            "LineId": "oLLTyBOR"
                        }, 
                        {
                            "LineFromName": "jwFzjrvw", 
                            "Bandwidth": 4, 
                            "LineToName": "mExjnDev", 
                            "LineFrom": "qIdsUACT", 
                            "LineTo": "kSdSlLJu", 
                            "LineId": "ZIPtWcEk"
                        }, 
                        {
                            "LineFromName": "vNyBQoXy", 
                            "Bandwidth": 7, 
                            "LineToName": "BMoIpFAY", 
                            "LineFrom": "ZmrxyhVV", 
                            "LineTo": "jQiOJYrb", 
                            "LineId": "YaGrYRwd"
                        }, 
                        {
                            "LineFromName": "IQzfMcHq", 
                            "Bandwidth": 4, 
                            "LineToName": "aBXyhKlJ", 
                            "LineFrom": "yAdDpOsF", 
                            "LineTo": "KUBZIQJq", 
                            "LineId": "IqhSmTPE"
                        }
                    ], 
                    "ExpireTime": 6, 
                    "CName": "agNZaaUg", 
                    "ChargeType": "Year", 
                    "UGAAId": "kaSOqYSZ", 
                    "IPList": [
                        "vGBJORHf", 
                        "jXveezAx", 
                        "VYKeqPwI", 
                        "UVKWTrlH", 
                        "iHbaGDuF", 
                        "kqLVnHTX", 
                        "beQBWKiM", 
                        "xWfjQrlU"
                    ], 
                    "CreateTime": 7
                }
            ]
        }, 
        {
            "UPathId": "GcHliaRP", 
            "Bandwidth": "oJZTwpaH", 
            "LineId": "NwdaRgsl", 
            "Name": "CkkqprwR", 
            "UGAAList": [
                {
                    "Status": "Available", 
                    "Domain": "GDJkEPLU", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }
                    ], 
                    "UGAAName": "hacDVDaD", 
                    "LineSet": [
                        {
                            "LineFromName": "coIqoCkh", 
                            "Bandwidth": 7, 
                            "LineToName": "EcReyuTs", 
                            "LineFrom": "sYXVmeuo", 
                            "LineTo": "ZRaPccqD", 
                            "LineId": "krecmlGO"
                        }, 
                        {
                            "LineFromName": "iZDxssxd", 
                            "Bandwidth": 3, 
                            "LineToName": "HYKkOXkX", 
                            "LineFrom": "YGsfHQOH", 
                            "LineTo": "OfoONQst", 
                            "LineId": "aXNbzKqv"
                        }, 
                        {
                            "LineFromName": "KzVNlPgK", 
                            "Bandwidth": 5, 
                            "LineToName": "KAzZmyeY", 
                            "LineFrom": "vBLhIbwh", 
                            "LineTo": "bBrStDMU", 
                            "LineId": "wSzjFnec"
                        }, 
                        {
                            "LineFromName": "UYQxzitc", 
                            "Bandwidth": 2, 
                            "LineToName": "oMqxQCbw", 
                            "LineFrom": "PtVVCZrh", 
                            "LineTo": "BXhRcwpf", 
                            "LineId": "yOJlixzo"
                        }, 
                        {
                            "LineFromName": "MSJatOxO", 
                            "Bandwidth": 6, 
                            "LineToName": "HJirUyHV", 
                            "LineFrom": "YYWmzqOh", 
                            "LineTo": "QnohOLyR", 
                            "LineId": "EOdMmEvi"
                        }, 
                        {
                            "LineFromName": "ipQEEXqn", 
                            "Bandwidth": 2, 
                            "LineToName": "VQQBFqFv", 
                            "LineFrom": "zCbrzHWG", 
                            "LineTo": "DacJUrKS", 
                            "LineId": "VCtaSZzA"
                        }, 
                        {
                            "LineFromName": "lrQzcbxp", 
                            "Bandwidth": 2, 
                            "LineToName": "ZzjQYIMQ", 
                            "LineFrom": "oKbyvoYD", 
                            "LineTo": "niDAzgXL", 
                            "LineId": "XwuNwDLK"
                        }, 
                        {
                            "LineFromName": "GCqfuQYx", 
                            "Bandwidth": 4, 
                            "LineToName": "meQVtBVB", 
                            "LineFrom": "UWEdnOkN", 
                            "LineTo": "BXgNGMIR", 
                            "LineId": "hZLsVJKj"
                        }
                    ], 
                    "ExpireTime": 4, 
                    "CName": "psWmzMeC", 
                    "ChargeType": "Year", 
                    "UGAAId": "MjXpnmvi", 
                    "IPList": [
                        "tCUdYCOb", 
                        "XCqNlJuP", 
                        "gYhICeTs", 
                        "boVrMWAE", 
                        "APQtMSEa"
                    ], 
                    "CreateTime": 7
                }, 
                {
                    "Status": "Available", 
                    "Domain": "uhHbiypb", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }
                    ], 
                    "UGAAName": "NXKhwIiA", 
                    "LineSet": [
                        {
                            "LineFromName": "kmbgvzxU", 
                            "Bandwidth": 9, 
                            "LineToName": "yaBFlqEU", 
                            "LineFrom": "vSfdtSwQ", 
                            "LineTo": "UdNajcWU", 
                            "LineId": "HNktzvbw"
                        }, 
                        {
                            "LineFromName": "myDGcNba", 
                            "Bandwidth": 4, 
                            "LineToName": "ovFHlBsj", 
                            "LineFrom": "bjEHFaOr", 
                            "LineTo": "ZiIFYDfS", 
                            "LineId": "xgcBdNLm"
                        }, 
                        {
                            "LineFromName": "jNRkgSmf", 
                            "Bandwidth": 4, 
                            "LineToName": "UtrOtqPo", 
                            "LineFrom": "LrFNAyHc", 
                            "LineTo": "UxJdoQPo", 
                            "LineId": "EhOjlOub"
                        }, 
                        {
                            "LineFromName": "BVVXFsrN", 
                            "Bandwidth": 8, 
                            "LineToName": "RAXjsCHo", 
                            "LineFrom": "auxkAZUa", 
                            "LineTo": "xSGUgvas", 
                            "LineId": "pOggLANU"
                        }, 
                        {
                            "LineFromName": "pJtnwfIz", 
                            "Bandwidth": 3, 
                            "LineToName": "UHADVAcg", 
                            "LineFrom": "cElpFlpn", 
                            "LineTo": "HeMJSObc", 
                            "LineId": "irIBelaC"
                        }, 
                        {
                            "LineFromName": "VukiPAhK", 
                            "Bandwidth": 8, 
                            "LineToName": "fvdEQnOr", 
                            "LineFrom": "jXUYaqiw", 
                            "LineTo": "EutjPxbW", 
                            "LineId": "MNyJvnHg"
                        }, 
                        {
                            "LineFromName": "OqwXNSvb", 
                            "Bandwidth": 3, 
                            "LineToName": "RTRidwiR", 
                            "LineFrom": "MkEabXFP", 
                            "LineTo": "cMHUIXHY", 
                            "LineId": "ToiQzaUM"
                        }, 
                        {
                            "LineFromName": "jwSpMxGF", 
                            "Bandwidth": 7, 
                            "LineToName": "vjerIxLH", 
                            "LineFrom": "NxDNTEFk", 
                            "LineTo": "iqSSWlke", 
                            "LineId": "dIcaLZpy"
                        }, 
                        {
                            "LineFromName": "cuLXtsQB", 
                            "Bandwidth": 3, 
                            "LineToName": "eFezvXPD", 
                            "LineFrom": "xZIkhcue", 
                            "LineTo": "jiigJREo", 
                            "LineId": "QjDVYrno"
                        }, 
                        {
                            "LineFromName": "smikaEtI", 
                            "Bandwidth": 9, 
                            "LineToName": "YgnpVXMN", 
                            "LineFrom": "jZzmvxMD", 
                            "LineTo": "wuMylmbj", 
                            "LineId": "DzdsBNWO"
                        }
                    ], 
                    "ExpireTime": 8, 
                    "CName": "mRZHFdcQ", 
                    "ChargeType": "Year", 
                    "UGAAId": "WsGiTUlw", 
                    "IPList": [
                        "EZTHakLL", 
                        "srXZPEvo", 
                        "MDAWyosO", 
                        "sQiZDPah"
                    ], 
                    "CreateTime": 9
                }, 
                {
                    "Status": "Available", 
                    "Domain": "YKMfzQYa", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }
                    ], 
                    "UGAAName": "CpODmBVe", 
                    "LineSet": [
                        {
                            "LineFromName": "IdLkwHEk", 
                            "Bandwidth": 1, 
                            "LineToName": "VcCHRGJZ", 
                            "LineFrom": "PLensjYt", 
                            "LineTo": "zNMJZpEm", 
                            "LineId": "IDObnoHQ"
                        }, 
                        {
                            "LineFromName": "kjsQMpeQ", 
                            "Bandwidth": 2, 
                            "LineToName": "xsDrjJpw", 
                            "LineFrom": "HAKNMbwb", 
                            "LineTo": "wzBXIjKV", 
                            "LineId": "CyFTkFic"
                        }, 
                        {
                            "LineFromName": "wuPJiqcG", 
                            "Bandwidth": 4, 
                            "LineToName": "vDwypidY", 
                            "LineFrom": "lxEzqOMB", 
                            "LineTo": "xDyAGLlU", 
                            "LineId": "WfUugkdT"
                        }, 
                        {
                            "LineFromName": "VEVolVYw", 
                            "Bandwidth": 1, 
                            "LineToName": "xqrBPico", 
                            "LineFrom": "XxNoPCIt", 
                            "LineTo": "bwvUiNtp", 
                            "LineId": "SYUQUXfT"
                        }
                    ], 
                    "ExpireTime": 2, 
                    "CName": "YaohpqEv", 
                    "ChargeType": "Year", 
                    "UGAAId": "qJGOMLAl", 
                    "IPList": [
                        "qXoEEVNf", 
                        "mexSpYMW", 
                        "xraEiaYo", 
                        "fKfrtcTP", 
                        "MmuqPZIh", 
                        "JCkjGYcY", 
                        "tVcvbrXN", 
                        "rcKvZObf", 
                        "OffpsurZ"
                    ], 
                    "CreateTime": 4
                }, 
                {
                    "Status": "Available", 
                    "Domain": "COuqCyto", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 2
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 6
                        }
                    ], 
                    "UGAAName": "MpAajCXq", 
                    "LineSet": [
                        {
                            "LineFromName": "VRPmsQUf", 
                            "Bandwidth": 3, 
                            "LineToName": "NSbszmwN", 
                            "LineFrom": "vIdWGmPh", 
                            "LineTo": "pFDFJtdT", 
                            "LineId": "WPLcpUSZ"
                        }, 
                        {
                            "LineFromName": "vkvlyoxH", 
                            "Bandwidth": 1, 
                            "LineToName": "EvHtXPXw", 
                            "LineFrom": "WEoTAqpD", 
                            "LineTo": "APkKYOGR", 
                            "LineId": "DeqoFTYq"
                        }, 
                        {
                            "LineFromName": "PPYpbTQU", 
                            "Bandwidth": 3, 
                            "LineToName": "bcfqODlB", 
                            "LineFrom": "uMhQsdUs", 
                            "LineTo": "jpqlqKDa", 
                            "LineId": "ixjlNSTf"
                        }, 
                        {
                            "LineFromName": "cOjPdHWS", 
                            "Bandwidth": 2, 
                            "LineToName": "klQFrILf", 
                            "LineFrom": "YQdNXhLg", 
                            "LineTo": "BRTPesJK", 
                            "LineId": "NbeHQMQM"
                        }, 
                        {
                            "LineFromName": "TqhcEfIb", 
                            "Bandwidth": 6, 
                            "LineToName": "tyjaTMUc", 
                            "LineFrom": "jrdEusau", 
                            "LineTo": "zsClSkBD", 
                            "LineId": "LpKGnrdo"
                        }, 
                        {
                            "LineFromName": "nLWRyJGW", 
                            "Bandwidth": 2, 
                            "LineToName": "YQaiZJTj", 
                            "LineFrom": "iUWcsfNh", 
                            "LineTo": "icNMcnIi", 
                            "LineId": "IJBQYEmn"
                        }, 
                        {
                            "LineFromName": "bRgFdwaE", 
                            "Bandwidth": 7, 
                            "LineToName": "bEBJeVpJ", 
                            "LineFrom": "XuXwGdsR", 
                            "LineTo": "NPeDuKIs", 
                            "LineId": "ENbIEedj"
                        }, 
                        {
                            "LineFromName": "LsWTBnbC", 
                            "Bandwidth": 6, 
                            "LineToName": "EPPEGgQB", 
                            "LineFrom": "GLZygALT", 
                            "LineTo": "fHgauIGT", 
                            "LineId": "yhtTjgPX"
                        }, 
                        {
                            "LineFromName": "yzsIKKcc", 
                            "Bandwidth": 1, 
                            "LineToName": "MkZtuAYt", 
                            "LineFrom": "nehtABjN", 
                            "LineTo": "QEgWxKnT", 
                            "LineId": "CYgedfBE"
                        }, 
                        {
                            "LineFromName": "kuUgEcbp", 
                            "Bandwidth": 3, 
                            "LineToName": "vjkjcNvx", 
                            "LineFrom": "YAuttHYL", 
                            "LineTo": "ayrumwOV", 
                            "LineId": "CNcRLLgO"
                        }
                    ], 
                    "ExpireTime": 5, 
                    "CName": "BFqFyWlR", 
                    "ChargeType": "Year", 
                    "UGAAId": "xoPUqEWd", 
                    "IPList": [
                        "rqwUzWCT", 
                        "efSjpgOU", 
                        "YvkWTopX", 
                        "KvfLiyoi", 
                        "AyMYruXF", 
                        "PXGMdlSS", 
                        "JfFsxPnp"
                    ], 
                    "CreateTime": 2
                }, 
                {
                    "Status": "Available", 
                    "Domain": "egslnvpt", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 4
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }
                    ], 
                    "UGAAName": "zlCFWHSa", 
                    "LineSet": [
                        {
                            "LineFromName": "HCrubtUk", 
                            "Bandwidth": 2, 
                            "LineToName": "rpiLKCtY", 
                            "LineFrom": "UCvmImTD", 
                            "LineTo": "hWcTALwS", 
                            "LineId": "nEoRIbzR"
                        }, 
                        {
                            "LineFromName": "THuPpOjI", 
                            "Bandwidth": 4, 
                            "LineToName": "NrOMgFGR", 
                            "LineFrom": "BveufUbi", 
                            "LineTo": "acvvxqgH", 
                            "LineId": "JQZcsGWm"
                        }
                    ], 
                    "ExpireTime": 4, 
                    "CName": "QiNcsJgo", 
                    "ChargeType": "Year", 
                    "UGAAId": "kUFqykaH", 
                    "IPList": [
                        "HdWlHZKi", 
                        "JypCCsQf", 
                        "YedGnRFP", 
                        "MZYASRgb", 
                        "gtjCJZYa", 
                        "EmnHFqtg", 
                        "uhmcAjvS", 
                        "hLclLknt"
                    ], 
                    "CreateTime": 3
                }, 
                {
                    "Status": "Available", 
                    "Domain": "ECIkiEtE", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 3
                        }
                    ], 
                    "UGAAName": "FSwjINsk", 
                    "LineSet": [
                        {
                            "LineFromName": "qPPSDCsm", 
                            "Bandwidth": 9, 
                            "LineToName": "JrOOyrRK", 
                            "LineFrom": "WeTjmRNH", 
                            "LineTo": "jNepBzVO", 
                            "LineId": "ypiCyrjV"
                        }, 
                        {
                            "LineFromName": "SBYqIGar", 
                            "Bandwidth": 9, 
                            "LineToName": "rXBKacDz", 
                            "LineFrom": "yuvJUVis", 
                            "LineTo": "nbtyjvUb", 
                            "LineId": "VvONulJL"
                        }, 
                        {
                            "LineFromName": "kknBZGgk", 
                            "Bandwidth": 8, 
                            "LineToName": "ITFerJnu", 
                            "LineFrom": "NpbtVsgg", 
                            "LineTo": "QmmltHxi", 
                            "LineId": "PAeSdEiA"
                        }, 
                        {
                            "LineFromName": "zmvsPCZl", 
                            "Bandwidth": 6, 
                            "LineToName": "tAYvHtqP", 
                            "LineFrom": "Hzwpjbpf", 
                            "LineTo": "NIHvgklh", 
                            "LineId": "UdqzJsEp"
                        }, 
                        {
                            "LineFromName": "RNyUgURa", 
                            "Bandwidth": 4, 
                            "LineToName": "HWlYCdCG", 
                            "LineFrom": "VGOQlbWL", 
                            "LineTo": "IGVbrUVr", 
                            "LineId": "EaSnFigW"
                        }, 
                        {
                            "LineFromName": "NlnENccm", 
                            "Bandwidth": 5, 
                            "LineToName": "GgrgDoIK", 
                            "LineFrom": "YXHYUqva", 
                            "LineTo": "pVsaUUsV", 
                            "LineId": "JpzcVrAA"
                        }, 
                        {
                            "LineFromName": "YCNMJpzl", 
                            "Bandwidth": 4, 
                            "LineToName": "jdfJXJvc", 
                            "LineFrom": "mYbEICjT", 
                            "LineTo": "afNdzemC", 
                            "LineId": "CABQXKqv"
                        }, 
                        {
                            "LineFromName": "ULpRtwvD", 
                            "Bandwidth": 3, 
                            "LineToName": "QvtKCyAH", 
                            "LineFrom": "iBlffycF", 
                            "LineTo": "qTWeXWYi", 
                            "LineId": "rWbYvCzv"
                        }, 
                        {
                            "LineFromName": "wBhbvxmL", 
                            "Bandwidth": 3, 
                            "LineToName": "QjmnryEy", 
                            "LineFrom": "rZFcZhnB", 
                            "LineTo": "jgUFQnVp", 
                            "LineId": "UGImFnRA"
                        }, 
                        {
                            "LineFromName": "qqHOltPR", 
                            "Bandwidth": 9, 
                            "LineToName": "DyyyoGtw", 
                            "LineFrom": "hsEwrNRr", 
                            "LineTo": "BrVxoaZx", 
                            "LineId": "IzthAgfr"
                        }
                    ], 
                    "ExpireTime": 1, 
                    "CName": "giTNmGNL", 
                    "ChargeType": "Year", 
                    "UGAAId": "rIGHMvOY", 
                    "IPList": [
                        "RZCvWDpa", 
                        "FSSSOwsK", 
                        "jIlPZYqQ", 
                        "eJNrnNUe", 
                        "AmGVpuCt", 
                        "QtcteZzm", 
                        "KhIppUTd", 
                        "VhcPJVfe", 
                        "ESYnLKYv", 
                        "vcfhcBDN"
                    ], 
                    "CreateTime": 4
                }, 
                {
                    "Status": "Available", 
                    "Domain": "mKqNAAuE", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 9
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 8
                        }
                    ], 
                    "UGAAName": "AfcBpNQF", 
                    "LineSet": [
                        {
                            "LineFromName": "dGLicLca", 
                            "Bandwidth": 8, 
                            "LineToName": "dTpcAuVl", 
                            "LineFrom": "bsFGAfzv", 
                            "LineTo": "ErHhMWym", 
                            "LineId": "ddONDVeo"
                        }, 
                        {
                            "LineFromName": "fvkDoJaj", 
                            "Bandwidth": 8, 
                            "LineToName": "SPhuTtch", 
                            "LineFrom": "qEeJqAAm", 
                            "LineTo": "LHmnrBZV", 
                            "LineId": "hyaiPPrI"
                        }, 
                        {
                            "LineFromName": "apdWVBEd", 
                            "Bandwidth": 7, 
                            "LineToName": "uWLUtoyq", 
                            "LineFrom": "jwfMJtrJ", 
                            "LineTo": "joNSqJrk", 
                            "LineId": "WHUFaEsb"
                        }, 
                        {
                            "LineFromName": "GTDxOWzC", 
                            "Bandwidth": 9, 
                            "LineToName": "GgXprMkq", 
                            "LineFrom": "LhdzDciG", 
                            "LineTo": "jIyTcLtV", 
                            "LineId": "MpyxdaNO"
                        }, 
                        {
                            "LineFromName": "dUFhYJwW", 
                            "Bandwidth": 4, 
                            "LineToName": "IjrUyivy", 
                            "LineFrom": "niJEwUIa", 
                            "LineTo": "RdLCVSDe", 
                            "LineId": "FKKbhEFh"
                        }, 
                        {
                            "LineFromName": "KogDcwxf", 
                            "Bandwidth": 7, 
                            "LineToName": "DGOtKTTd", 
                            "LineFrom": "VDsTptiy", 
                            "LineTo": "xBUzjPkU", 
                            "LineId": "nZAZjMJT"
                        }, 
                        {
                            "LineFromName": "nxoJhjiI", 
                            "Bandwidth": 7, 
                            "LineToName": "nfGqomkL", 
                            "LineFrom": "DjZsICwS", 
                            "LineTo": "OlqVRecH", 
                            "LineId": "TqCXzBRS"
                        }, 
                        {
                            "LineFromName": "ujdKYFbb", 
                            "Bandwidth": 8, 
                            "LineToName": "pImlfPJx", 
                            "LineFrom": "rDDgfHWr", 
                            "LineTo": "GSYogjHJ", 
                            "LineId": "WdUDgLDt"
                        }, 
                        {
                            "LineFromName": "rYmIvORQ", 
                            "Bandwidth": 9, 
                            "LineToName": "UkKeJvvi", 
                            "LineFrom": "EIGmmvJT", 
                            "LineTo": "ZBkuEDZE", 
                            "LineId": "GwWRjTzw"
                        }
                    ], 
                    "ExpireTime": 4, 
                    "CName": "cUjXHDNn", 
                    "ChargeType": "Year", 
                    "UGAAId": "qXxPZdRO", 
                    "IPList": [
                        "mIwxoeqd", 
                        "KQVffJSR", 
                        "HuiICFkr"
                    ], 
                    "CreateTime": 2
                }, 
                {
                    "Status": "Available", 
                    "Domain": "vPQqHefA", 
                    "TaskSet": [
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 7
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 5
                        }, 
                        {
                            "Status": "Available", 
                            "Protocol": "TCP", 
                            "Port": 1
                        }
                    ], 
                    "UGAAName": "PrBEKLnB", 
                    "LineSet": [
                        {
                            "LineFromName": "SLPIiCuI", 
                            "Bandwidth": 3, 
                            "LineToName": "xdAFxoWi", 
                            "LineFrom": "PzlAvGjC", 
                            "LineTo": "ubRhjwxH", 
                            "LineId": "lFklIWWN"
                        }, 
                        {
                            "LineFromName": "OSrRnrWr", 
                            "Bandwidth": 3, 
                            "LineToName": "gZcCSwHT", 
                            "LineFrom": "tSvchBpp", 
                            "LineTo": "GDRZgeqU", 
                            "LineId": "QCSODkwC"
                        }, 
                        {
                            "LineFromName": "TFoTlQhI", 
                            "Bandwidth": 8, 
                            "LineToName": "nzOBkycZ", 
                            "LineFrom": "fNkqzEAT", 
                            "LineTo": "mjoKTcdj", 
                            "LineId": "jumHduKO"
                        }, 
                        {
                            "LineFromName": "fuTfRbFR", 
                            "Bandwidth": 9, 
                            "LineToName": "VbTyjNro", 
                            "LineFrom": "YfziBFpL", 
                            "LineTo": "xuWwiben", 
                            "LineId": "jUkxjNDl"
                        }
                    ], 
                    "ExpireTime": 3, 
                    "CName": "RhKxItGB", 
                    "ChargeType": "Year", 
                    "UGAAId": "KgOgJzYt", 
                    "IPList": [
                        "xjfcWIKB", 
                        "MBURedke"
                    ], 
                    "CreateTime": 4
                }
            ]
        }
    ], 
    "Action": "DescribeUPathResponse", 
    "RetCode": 0
}
```

