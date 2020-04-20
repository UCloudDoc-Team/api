# 获取物理云机型信息-DescribePHostMachineType

获取物理云机型的详细描述信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Type|string|具体机型。若不填写，则返回全部机型|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|MachineTypes|array|机型列表，模型：PHostMachineTypeSet|**Yes**|

## PHostMachineTypeSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Type|string|物理云主机机型别名，全网唯一。|**Yes**|
|Name|string|机型名|No|
|CPU|object|CPU信息|No|
|Memory|int|内存大小，单位GB|No|
|Disks|array|磁盘信息|No|
|Components|object|其他组件信息|No|
|Clusters|array|集群库存信息|No|
|RaidSupported|string|是否支持Raid。枚举值：支持：YES；不支持：NO|No|

## PHostCPUSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Model|string|CPU型号|No|
|Frequence|float|CPU主频|No|
|Count|int|CPU个数|No|
|CoreCount|int|CPU核数|No|

## PHostDiskSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Space|int|单盘大小，单位GB|No|
|Count|int|磁盘数量|No|
|Type|string|磁盘属性|No|
|Name|string|磁盘名称，sys/data|No|
|IOCap|int|磁盘IO性能，单位MB/s（待废弃）|No|

## PHostComponentSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|组件名称|No|
|Count|string|组件数量|No|

## PHostClusterSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|集群名。枚举值：千兆网络集群：1G；万兆网络集群：10G|No|
|StockStatus|string|库存状态。枚举值：有库存：Available；无库存：SoldOut|No|

# Request Example
```
https://api.ucloud.cn/?Action=DecribePHostMachineType
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId =detQFgay
```

# Response Example
```
{
    "Action": "DecribePHostMachineTypeResponse", 
    "MachineTypes": [
        {
            "Name": "zpTlETUH", 
            "Disks": [
                {
                    "Count": 2, 
                    "IOCap": 5, 
                    "Name": "dBYZcRhT", 
                    "Space": "sTYQFgHi", 
                    "Type": "vWncBZiN", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 3, 
                    "IOCap": 6, 
                    "Name": "VBBrKhTk", 
                    "Space": "DdJQurYS", 
                    "Type": "nvhCJrAM", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 2, 
                    "IOCap": 8, 
                    "Name": "AWJmnHbV", 
                    "Space": "YmHkZQaF", 
                    "Type": "exvByBwT", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 9, 
                    "IOCap": 3, 
                    "Name": "LdyKQSmL", 
                    "Space": "UNimVdja", 
                    "Type": "yUCFkkVL", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 5, 
                    "IOCap": 3, 
                    "Name": "rchNbVhm", 
                    "Space": "rECnDhPQ", 
                    "Type": "ciMqEkoM", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 2, 
                    "IOCap": 3, 
                    "Name": "oteQABCf", 
                    "Space": "HlgmqbWE", 
                    "Type": "tukbcSYM", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 8, 
                    "IOCap": 6, 
                    "Name": "KYaFudEP", 
                    "Space": "RnfRCFih", 
                    "Type": "tVGQSlPW", 
                    "IsBootDisk": false
                }
            ], 
            "RAMs": [
                {
                    "Count": "CiPhmPRx", 
                    "Size": "YqhwqfNV"
                }, 
                {
                    "Count": "eWndxrvc", 
                    "Size": "xWwmIqjz"
                }, 
                {
                    "Count": "VGdRynZl", 
                    "Size": "FvnAzbTI"
                }, 
                {
                    "Count": "XNKSaVjL", 
                    "Size": "KZwbPOxS"
                }, 
                {
                    "Count": "PvTNcUcA", 
                    "Size": "AZdLfVkn"
                }, 
                {
                    "Count": "TqgZUQhN", 
                    "Size": "FDmCDglM"
                }, 
                {
                    "Count": "urYFlEVb", 
                    "Size": "ZqhareaU"
                }
            ], 
            "Alias": "dJzJPwiX", 
            "Components": [
                {
                    "Count": "VgEvDALX", 
                    "Name": "OIzmCMWh"
                }, 
                {
                    "Count": "MxfQLvlb", 
                    "Name": "wkgtJrxy"
                }, 
                {
                    "Count": "lXevJgZx", 
                    "Name": "lHjTZFfF"
                }, 
                {
                    "Count": "ZcdzCzOu", 
                    "Name": "GcbSWfia"
                }
            ], 
            "Clusters": [
                "HOxxPtaN", 
                "oewcdIGS", 
                "jwFRAJYj", 
                "CzcpkyqH", 
                "xNvMrMqw", 
                "AtJIiMvC", 
                "doEMjuZB", 
                "FkYEUGBE", 
                "eZbJGgwL"
            ], 
            "CPU": {}
        }, 
        {
            "Name": "VysGJpEG", 
            "Disks": [
                {
                    "Count": 6, 
                    "IOCap": 3, 
                    "Name": "MuZqlxJE", 
                    "Space": "WkcqbkWo", 
                    "Type": "tENZbjVs", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 1, 
                    "IOCap": 4, 
                    "Name": "EuMlyaSp", 
                    "Space": "HIPaRInw", 
                    "Type": "gJlDwddO", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 9, 
                    "IOCap": 3, 
                    "Name": "zLrcKCUx", 
                    "Space": "Mtnjycbv", 
                    "Type": "ppvVmCHY", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 5, 
                    "IOCap": 2, 
                    "Name": "UbXkcmGm", 
                    "Space": "xSZcithr", 
                    "Type": "HNRzYJtp", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 1, 
                    "IOCap": 2, 
                    "Name": "JfROmWBQ", 
                    "Space": "YloFsYcT", 
                    "Type": "irsyxZzM", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 7, 
                    "IOCap": 6, 
                    "Name": "ckMhQUwl", 
                    "Space": "oNDQceBY", 
                    "Type": "hXULrsez", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 1, 
                    "IOCap": 8, 
                    "Name": "ktONSdcy", 
                    "Space": "UwkbAeTq", 
                    "Type": "VvvkdIYd", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 9, 
                    "IOCap": 2, 
                    "Name": "PPPdisTW", 
                    "Space": "gpvGVCGw", 
                    "Type": "cXnAWqIu", 
                    "IsBootDisk": false
                }
            ], 
            "RAMs": [
                {
                    "Count": "EqLhuqqn", 
                    "Size": "EOHLNfRW"
                }, 
                {
                    "Count": "TiszVCjU", 
                    "Size": "sWsXwcDO"
                }, 
                {
                    "Count": "cGJlSNLC", 
                    "Size": "WWlCyjIT"
                }
            ], 
            "Alias": "HVdcDyhI", 
            "Components": [
                {
                    "Count": "MRXduVvB", 
                    "Name": "utJnxjNF"
                }, 
                {
                    "Count": "HhBTEuci", 
                    "Name": "fAfEmWwg"
                }, 
                {
                    "Count": "dReuMMNs", 
                    "Name": "HdVMURwp"
                }, 
                {
                    "Count": "AcMyBYlL", 
                    "Name": "GoxKoGrt"
                }, 
                {
                    "Count": "FlICQuYC", 
                    "Name": "WMgqDUpr"
                }, 
                {
                    "Count": "KahFOTkA", 
                    "Name": "jRfloCMN"
                }, 
                {
                    "Count": "tVRJHbNg", 
                    "Name": "PQtKhdbU"
                }, 
                {
                    "Count": "hNhEOKxv", 
                    "Name": "HJypZssG"
                }
            ], 
            "Clusters": [
                "dkeDmxKL", 
                "NiUqjmYk", 
                "xeEDwdfQ"
            ], 
            "CPU": {}
        }, 
        {
            "Name": "xlGzYMxG", 
            "Disks": [
                {
                    "Count": 7, 
                    "IOCap": 4, 
                    "Name": "jYNSYzKC", 
                    "Space": "AkWgSjcB", 
                    "Type": "yTMzoNfq", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 4, 
                    "IOCap": 4, 
                    "Name": "TKdacDdJ", 
                    "Space": "ozvRYkOy", 
                    "Type": "WasmIuxH", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 4, 
                    "IOCap": 5, 
                    "Name": "JWwYCLlV", 
                    "Space": "YzitZYny", 
                    "Type": "nZoGNQkg", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 7, 
                    "IOCap": 1, 
                    "Name": "BSqMiuUe", 
                    "Space": "zuaFXdBC", 
                    "Type": "rfsjCIgt", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 9, 
                    "IOCap": 6, 
                    "Name": "RBjkjzfo", 
                    "Space": "cZwfiyKP", 
                    "Type": "mlchrKHk", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 1, 
                    "IOCap": 4, 
                    "Name": "LPfBupIr", 
                    "Space": "ttbHmAAb", 
                    "Type": "dpHzYDnl", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 9, 
                    "IOCap": 3, 
                    "Name": "jeiWjcQC", 
                    "Space": "GulNCjGe", 
                    "Type": "llREfoZS", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 5, 
                    "IOCap": 8, 
                    "Name": "XtymBqsL", 
                    "Space": "KvpQRmTu", 
                    "Type": "Dvucsgxs", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 8, 
                    "IOCap": 7, 
                    "Name": "EUzGPeIc", 
                    "Space": "usebgAvn", 
                    "Type": "iDsSCzNs", 
                    "IsBootDisk": false
                }
            ], 
            "RAMs": [
                {
                    "Count": "LwUtoWxx", 
                    "Size": "PfSlCLma"
                }, 
                {
                    "Count": "LIQcBjWq", 
                    "Size": "hTssRBCv"
                }, 
                {
                    "Count": "DnqeLmbM", 
                    "Size": "SQfepQjm"
                }, 
                {
                    "Count": "goeJomxp", 
                    "Size": "tHbCKylf"
                }, 
                {
                    "Count": "FKiFfNMV", 
                    "Size": "AdXPnWxa"
                }, 
                {
                    "Count": "ZHNzYHIx", 
                    "Size": "cOnVtnZM"
                }, 
                {
                    "Count": "nUaACKXg", 
                    "Size": "nFDGQrbC"
                }, 
                {
                    "Count": "RqfXGdVz", 
                    "Size": "KDTHqdXq"
                }
            ], 
            "Alias": "IzGqwkyD", 
            "Components": [
                {
                    "Count": "eYcahTfs", 
                    "Name": "JkwCYetV"
                }, 
                {
                    "Count": "KyIdhAZK", 
                    "Name": "eWWtkyTO"
                }, 
                {
                    "Count": "yCMlHWUd", 
                    "Name": "DheBjNnp"
                }
            ], 
            "Clusters": [
                "wUHLrAxX", 
                "nLrePRXR", 
                "BWuzShCk", 
                "iErMEnkz", 
                "IRChAPQh"
            ], 
            "CPU": {}
        }, 
        {
            "Name": "goZgINhG", 
            "Disks": [
                {
                    "Count": 4, 
                    "IOCap": 8, 
                    "Name": "KXTNGvFW", 
                    "Space": "xmxdnLbd", 
                    "Type": "qvlLQvqo", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 9, 
                    "IOCap": 9, 
                    "Name": "jRRPSCuQ", 
                    "Space": "UbVbPyyV", 
                    "Type": "qZnDSAzg", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 2, 
                    "IOCap": 4, 
                    "Name": "zMoDqBfI", 
                    "Space": "LwLHMYPN", 
                    "Type": "egJUZqgL", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 7, 
                    "IOCap": 8, 
                    "Name": "LkckCSxZ", 
                    "Space": "vFvrsFLL", 
                    "Type": "rXMRyflt", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 8, 
                    "IOCap": 1, 
                    "Name": "ENSgqSZs", 
                    "Space": "xtwzTbFZ", 
                    "Type": "kUDmtpAy", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 7, 
                    "IOCap": 8, 
                    "Name": "rzRRDiwD", 
                    "Space": "AUBFIDtQ", 
                    "Type": "zgtJMJJP", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 4, 
                    "IOCap": 3, 
                    "Name": "CejKNeaJ", 
                    "Space": "UylObvWG", 
                    "Type": "onZpJaTj", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 6, 
                    "IOCap": 4, 
                    "Name": "pygFIjdD", 
                    "Space": "oaAmSaPT", 
                    "Type": "JlIPSFUk", 
                    "IsBootDisk": false
                }
            ], 
            "RAMs": [
                {
                    "Count": "jVAoRETs", 
                    "Size": "GxcZNwCW"
                }, 
                {
                    "Count": "DxgXiIXn", 
                    "Size": "WDctkabp"
                }, 
                {
                    "Count": "PBKoSkgS", 
                    "Size": "YDCfsran"
                }
            ], 
            "Alias": "CpXPXpfg", 
            "Components": [
                {
                    "Count": "GWAoWbur", 
                    "Name": "MEcYBieJ"
                }, 
                {
                    "Count": "mQNphGJH", 
                    "Name": "iZSUQQRe"
                }
            ], 
            "Clusters": [
                "YGdzGCRs", 
                "qAESfdmF", 
                "joqwomlk", 
                "ILThrukz", 
                "cXPuLVye", 
                "tDrGuKyR"
            ], 
            "CPU": {}
        }, 
        {
            "Name": "XWIpnckX", 
            "Disks": [
                {
                    "Count": 5, 
                    "IOCap": 2, 
                    "Name": "WfdcwwTZ", 
                    "Space": "PNWOURdk", 
                    "Type": "UjgLslAw", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 8, 
                    "IOCap": 5, 
                    "Name": "qjlOIWdy", 
                    "Space": "xKXBkjqx", 
                    "Type": "MXrtIkGb", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 9, 
                    "IOCap": 4, 
                    "Name": "tAiVaCMD", 
                    "Space": "wQZBfQuQ", 
                    "Type": "vcVfhauB", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 3, 
                    "IOCap": 1, 
                    "Name": "OtiSboZr", 
                    "Space": "AzZduaVn", 
                    "Type": "iAXpuMkS", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 8, 
                    "IOCap": 3, 
                    "Name": "PZkedOPz", 
                    "Space": "feJsngXx", 
                    "Type": "FLRZJJTP", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 9, 
                    "IOCap": 1, 
                    "Name": "wbVDDnKL", 
                    "Space": "yAPbqjdQ", 
                    "Type": "zikfKQSM", 
                    "IsBootDisk": false
                }
            ], 
            "RAMs": [
                {
                    "Count": "pUNWdhim", 
                    "Size": "EadrOhUI"
                }, 
                {
                    "Count": "qOFKYZiW", 
                    "Size": "csfujfEX"
                }
            ], 
            "Alias": "HWXDAMVN", 
            "Components": [
                {
                    "Count": "MlosaHao", 
                    "Name": "KkFMMOwb"
                }, 
                {
                    "Count": "JEvjLGEH", 
                    "Name": "UpRjmUDR"
                }, 
                {
                    "Count": "yVVJmJWP", 
                    "Name": "XLkXZkCr"
                }
            ], 
            "Clusters": [
                "PfeWXQoq", 
                "NrNndXDb", 
                "pcFOEyOK", 
                "ZfFmVzHL", 
                "KWorNlYL", 
                "pXMKTgov", 
                "InzUnmCe", 
                "XRqHRgNQ"
            ], 
            "CPU": {}
        }, 
        {
            "Name": "QTYMYTpk", 
            "Disks": [
                {
                    "Count": 1, 
                    "IOCap": 6, 
                    "Name": "pbBjNOln", 
                    "Space": "AABzZyUv", 
                    "Type": "GqMLPpMO", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 3, 
                    "IOCap": 9, 
                    "Name": "DeHztoAT", 
                    "Space": "VcOvMylR", 
                    "Type": "ZsbvxiUl", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 6, 
                    "IOCap": 6, 
                    "Name": "ofMJRwEv", 
                    "Space": "uYDCIHzO", 
                    "Type": "VxqHexQW", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 4, 
                    "IOCap": 8, 
                    "Name": "JdCdaJOj", 
                    "Space": "ZVJIeIBB", 
                    "Type": "WmeUqXDZ", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 6, 
                    "IOCap": 6, 
                    "Name": "hclvhRqz", 
                    "Space": "sTvvVoJI", 
                    "Type": "FPgfAAiN", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 7, 
                    "IOCap": 6, 
                    "Name": "iasFPmhi", 
                    "Space": "pOAcsJht", 
                    "Type": "RflKUtlY", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 4, 
                    "IOCap": 5, 
                    "Name": "pvtnzTsZ", 
                    "Space": "DkVyqUqL", 
                    "Type": "bXOadkCN", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 4, 
                    "IOCap": 4, 
                    "Name": "oauHGxBo", 
                    "Space": "lvMaIdfp", 
                    "Type": "vCohuIAC", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 4, 
                    "IOCap": 5, 
                    "Name": "iWVvMBXQ", 
                    "Space": "OCmAXNoD", 
                    "Type": "gvuPQwAq", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 2, 
                    "IOCap": 6, 
                    "Name": "TXBGojLN", 
                    "Space": "OPVPksia", 
                    "Type": "YPLNDfPP", 
                    "IsBootDisk": false
                }
            ], 
            "RAMs": [
                {
                    "Count": "DbMrnzud", 
                    "Size": "ItvdHrsb"
                }, 
                {
                    "Count": "pyyzOsgQ", 
                    "Size": "MnmHPQzA"
                }, 
                {
                    "Count": "ZIiScngx", 
                    "Size": "gHDXRUVu"
                }, 
                {
                    "Count": "gutcXuiK", 
                    "Size": "CDmBfALM"
                }, 
                {
                    "Count": "osADDsYs", 
                    "Size": "vWdwAcxU"
                }, 
                {
                    "Count": "GBVGNnfj", 
                    "Size": "WBxJHIns"
                }, 
                {
                    "Count": "RhNRjrXY", 
                    "Size": "ihPuWuKs"
                }, 
                {
                    "Count": "vumeGTpa", 
                    "Size": "uScPvVme"
                }, 
                {
                    "Count": "akZTIxKL", 
                    "Size": "EBOBqbBR"
                }
            ], 
            "Alias": "vuStHgWi", 
            "Components": [
                {
                    "Count": "sBvqvSmK", 
                    "Name": "uUSYGQgT"
                }, 
                {
                    "Count": "czcrRdXD", 
                    "Name": "ZozSmnxY"
                }, 
                {
                    "Count": "udWxzMNc", 
                    "Name": "suMXoSKu"
                }, 
                {
                    "Count": "RdGOPaeh", 
                    "Name": "JhYTqZaJ"
                }, 
                {
                    "Count": "pHzMtRnR", 
                    "Name": "cIovBVGJ"
                }, 
                {
                    "Count": "lGDRPcAV", 
                    "Name": "IfvBFhtC"
                }, 
                {
                    "Count": "UkPLmZrv", 
                    "Name": "wFqOzskr"
                }, 
                {
                    "Count": "vtSkQvIh", 
                    "Name": "ZusFrwiV"
                }, 
                {
                    "Count": "sDJgrhCz", 
                    "Name": "ZuKSCJAa"
                }
            ], 
            "Clusters": [
                "fxsXiWdb", 
                "NtsvPiBI", 
                "mGkcikhH", 
                "pnELxLql", 
                "fykTfFqm"
            ], 
            "CPU": {}
        }, 
        {
            "Name": "JPNrgwFN", 
            "Disks": [
                {
                    "Count": 8, 
                    "IOCap": 1, 
                    "Name": "KIFAYxSe", 
                    "Space": "rRKOgVqh", 
                    "Type": "QXJTeZsy", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 6, 
                    "IOCap": 6, 
                    "Name": "SEDqJQRp", 
                    "Space": "rSDZGlXx", 
                    "Type": "tFydDrvx", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 7, 
                    "IOCap": 1, 
                    "Name": "WpNxLCIS", 
                    "Space": "sKAQtKiv", 
                    "Type": "zQApKMqZ", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 9, 
                    "IOCap": 7, 
                    "Name": "JTRycftY", 
                    "Space": "FkJaeDpX", 
                    "Type": "aubLDato", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 8, 
                    "IOCap": 9, 
                    "Name": "jGCpAsse", 
                    "Space": "DcHoFbge", 
                    "Type": "KzwhCFpy", 
                    "IsBootDisk": true
                }, 
                {
                    "Count": 4, 
                    "IOCap": 1, 
                    "Name": "bElBsojV", 
                    "Space": "MHUMcTmX", 
                    "Type": "oOqwDYDk", 
                    "IsBootDisk": false
                }, 
                {
                    "Count": 9, 
                    "IOCap": 9, 
                    "Name": "tRexyOLi", 
                    "Space": "TQaiKLeL", 
                    "Type": "OHMDTtKA", 
                    "IsBootDisk": true
                }
            ], 
            "RAMs": [
                {
                    "Count": "vbXEfYYc", 
                    "Size": "VOuSHlOj"
                }, 
                {
                    "Count": "ZpuBZjlP", 
                    "Size": "cxkAwium"
                }, 
                {
                    "Count": "cNHlBnLt", 
                    "Size": "TBRBdcip"
                }
            ], 
            "Alias": "oBJXfmdz", 
            "Components": [
                {
                    "Count": "nokQworP", 
                    "Name": "rmxxjwDh"
                }, 
                {
                    "Count": "oGVVCeKo", 
                    "Name": "sIyvKEZX"
                }, 
                {
                    "Count": "FKFWmDTX", 
                    "Name": "oSLbgEYl"
                }, 
                {
                    "Count": "UDDgSrjU", 
                    "Name": "anmzKYVa"
                }
            ], 
            "Clusters": [
                "dcAcnZTX", 
                "XvUuLuQL", 
                "ffxBPZGq", 
                "FRYydQRc", 
                "tfgwdfGi", 
                "SrrxfjbY", 
                "KYQxOBxQ", 
                "EyLGWbDB", 
                "OoxOhTPc"
            ], 
            "CPU": {}
        }
    ], 
    "RetCode": 0
}
```

