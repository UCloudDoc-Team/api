#描述硬件隔离组-DescribeIsolationGroup

描述硬件隔离组

#Request Parameters
|Parameter name|Type|Description|Required|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目id|No|
|GroupId|string|要查询的硬件隔离组id|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20，最大100|No|


#Response Elements
|Parameter name|Type|Description|Required|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|IsolationGroupSet|array|硬件隔离组集合，参考IsolationGroup|No|


##IsolationGroup
|Parameter name|Type|Description|Required|
|GroupName|string|硬件隔离组名称|No|
|GroupId|string|硬件隔离组id|No|
|SpreadInfoSet|array|每个可用区中的机器数量，参考SpreadInfo|No|
|Remark|string|备注|No|


##SpreadInfo
|Parameter name|Type|Description|Required|
|Zone|string|可用区信息|No|
|UHostCount|int|可用区中硬件隔离组中云主机的数量，不超过7。|No|

#Request Example
```
https://api.ucloud.cn/?Action=DescribeIsolationGroup
&Region=cn-zj
&GroupId=eoLEQOOy
&ProjectId=UAfwElsL
&Offset=4
&Limit=3
```
#Response Example
```
{
    "RetCode": 0,
    "Action": "DescribeIsolationGroupResponse",
    "IsolationGroupSet": [
        {
            "GroupName": "FfjAvODP",
            "GroupId": "sYCGPSVa",
            "SpreadInfoSet": [
                {
                    "Zone": "ckzKEzju",
                    "UHostCount": 4
                },
                {
                    "Zone": "JxJjJLEh",
                    "UHostCount": 4
                },
                {
                    "Zone": "vfeWwork",
                    "UHostCount": 1
                },
                {
                    "Zone": "mdDSKRtP",
                    "UHostCount": 7
                },
                {
                    "Zone": "ckmKtCkf",
                    "UHostCount": 7
                },
                {
                    "Zone": "fdyQiLJX",
                    "UHostCount": 7
                },
                {
                    "Zone": "bnpHtcVh",
                    "UHostCount": 6
                },
                {
                    "Zone": "tlgxSexx",
                    "UHostCount": 7
                },
                {
                    "Zone": "DknEPTTQ",
                    "UHostCount": 7
                }
            ]
        },
        {
            "GroupName": "waQcuepq",
            "GroupId": "dUtmePjp",
            "SpreadInfoSet": [
                {
                    "Zone": "RIkhPcmF",
                    "UHostCount": 2
                },
                {
                    "Zone": "ZZiDAcUQ",
                    "UHostCount": 6
                },
                {
                    "Zone": "LxwjPKkC",
                    "UHostCount": 6
                },
                {
                    "Zone": "EICjITTU",
                    "UHostCount": 6
                },
                {
                    "Zone": "LvRzXMqO",
                    "UHostCount": 4
                },
                {
                    "Zone": "hsNbrfIO",
                    "UHostCount": 1
                },
                {
                    "Zone": "vLxZmVpQ",
                    "UHostCount": 6
                },
                {
                    "Zone": "YaqMHcyT",
                    "UHostCount": 7
                },
                {
                    "Zone": "VkTcAsom",
                    "UHostCount": 7
                },
                {
                    "Zone": "osJUBzQs",
                    "UHostCount": 7
                }
            ]
        },
        {
            "GroupName": "BuRDNSMV",
            "GroupId": "PNbUMSnT",
            "SpreadInfoSet": [
                {
                    "Zone": "FqzxOwWF",
                    "UHostCount": 1
                },
                {
                    "Zone": "TYJXNABc",
                    "UHostCount": 7
                },
                {
                    "Zone": "TmifjmqF",
                    "UHostCount": 2
                },
                {
                    "Zone": "ynTmVgAX",
                    "UHostCount": 6
                },
                {
                    "Zone": "VpulfwsB",
                    "UHostCount": 3
                },
                {
                    "Zone": "GmkCwqKR",
                    "UHostCount": 7
                },
                {
                    "Zone": "dDKSifpU",
                    "UHostCount": 7
                },
                {
                    "Zone": "UrGHZufJ",
                    "UHostCount": 5
                },
                {
                    "Zone": "gUdvtgFE",
                    "UHostCount": 5
                }
            ]
        },
        {
            "GroupName": "GLKfEBHo",
            "GroupId": "YRMkPcpS",
            "SpreadInfoSet": [
                {
                    "Zone": "XHgsxqdg",
                    "UHostCount": 5
                },
                {
                    "Zone": "iRQKLaRj",
                    "UHostCount": 6
                },
                {
                    "Zone": "vFgPUUjt",
                    "UHostCount": 7
                },
                {
                    "Zone": "BNWmMVpg",
                    "UHostCount": 4
                },
                {
                    "Zone": "DeXHKBzt",
                    "UHostCount": 1
                },
                {
                    "Zone": "avAFYxlI",
                    "UHostCount": 7
                },
                {
                    "Zone": "sPwawXVS",
                    "UHostCount": 3
                },
                {
                    "Zone": "XPOommle",
                    "UHostCount": 7
                },
                {
                    "Zone": "sDVWXwoD",
                    "UHostCount": 7
                },
                {
                    "Zone": "NHWKWBmr",
                    "UHostCount": 7
                }
            ]
        },
        {
            "GroupName": "YQRxjUUP",
            "GroupId": "KbqAWrnZ",
            "SpreadInfoSet": [
                {
                    "Zone": "ybcvUHGg",
                    "UHostCount": 7
                },
                {
                    "Zone": "bNCfdMfU",
                    "UHostCount": 2
                }
            ]
        },
        {
            "GroupName": "PoNhklah",
            "GroupId": "VvKIjAoJ",
            "SpreadInfoSet": [
                {
                    "Zone": "jtsvJBwo",
                    "UHostCount": 1
                },
                {
                    "Zone": "amlZMtpF",
                    "UHostCount": 2
                },
                {
                    "Zone": "RqGIAweJ",
                    "UHostCount": 5
                },
                {
                    "Zone": "ZUmCMgmh",
                    "UHostCount": 2
                },
                {
                    "Zone": "DHLgKKsN",
                    "UHostCount": 7
                },
                {
                    "Zone": "khBlCYDN",
                    "UHostCount": 1
                },
                {
                    "Zone": "aKZoaKxv",
                    "UHostCount": 7
                },
                {
                    "Zone": "XKwieRxS",
                    "UHostCount": 7
                },
                {
                    "Zone": "ZztdlMSY",
                    "UHostCount": 1
                },
                {
                    "Zone": "beGvpfXk",
                    "UHostCount": 3
                }
            ]
        },
        {
            "GroupName": "SPFppiav",
            "GroupId": "wYyaBPCv",
            "SpreadInfoSet": [
                {
                    "Zone": "sHRTtqXY",
                    "UHostCount": 2
                },
                {
                    "Zone": "IOyDEHtK",
                    "UHostCount": 6
                },
                {
                    "Zone": "qCWALWUq",
                    "UHostCount": 2
                },
                {
                    "Zone": "xWfLsowE",
                    "UHostCount": 4
                },
                {
                    "Zone": "hpvNNHce",
                    "UHostCount": 2
                },
                {
                    "Zone": "cJUybjFR",
                    "UHostCount": 5
                },
                {
                    "Zone": "mVDidZHk",
                    "UHostCount": 2
                },
                {
                    "Zone": "zbyPAXxR",
                    "UHostCount": 2
                },
                {
                    "Zone": "PxaozvKP",
                    "UHostCount": 6
                },
                {
                    "Zone": "BPfzdZlb",
                    "UHostCount": 5
                }
            ]
        },
        {
            "GroupName": "GhNYJpke",
            "GroupId": "cILearzD",
            "SpreadInfoSet": [
                {
                    "Zone": "NlJbuwsv",
                    "UHostCount": 4
                },
                {
                    "Zone": "JiDJVDmu",
                    "UHostCount": 6
                },
                {
                    "Zone": "reyxDucL",
                    "UHostCount": 3
                },
                {
                    "Zone": "BCanlmvA",
                    "UHostCount": 5
                },
                {
                    "Zone": "ahWxmqUD",
                    "UHostCount": 4
                },
                {
                    "Zone": "JxDibZhh",
                    "UHostCount": 7
                },
                {
                    "Zone": "TjYOutYX",
                    "UHostCount": 1
                }
            ]
        },
        {
            "GroupName": "chrixSUu",
            "GroupId": "ppLfBQrd",
            "SpreadInfoSet": [
                {
                    "Zone": "HPCwJiXb",
                    "UHostCount": 2
                },
                {
                    "Zone": "QUqJKHmy",
                    "UHostCount": 4
                }
            ]
        },
        {
            "GroupName": "UPZRkjRv",
            "GroupId": "ZRjkgaqr",
            "SpreadInfoSet": [
                {
                    "Zone": "CXNrjCEU",
                    "UHostCount": 1
                },
                {
                    "Zone": "aYcMlSSf",
                    "UHostCount": 7
                },
                {
                    "Zone": "gorleIqQ",
                    "UHostCount": 7
                },
                {
                    "Zone": "WSpdvKHZ",
                    "UHostCount": 2
                }
            ]
        }
    ]
}
```

{{indexmenu_n>1000}}