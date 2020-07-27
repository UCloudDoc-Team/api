# 查询硬件隔离组 - DescribeIsolationGroup

## 简介

查询硬件隔离组列表。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeIsolationGroup)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeIsolationGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目id |No|
| **GroupId** | string | 待查的硬件隔离组id |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **IsolationGroupSet** | array[[*IsolationGroup*](#IsolationGroup)] | 硬件隔离组集合。参见数据结构IsolationGroup。 |No|

#### 数据模型


#### IsolationGroup

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GroupName** | string | 硬件隔离组名称 |No|
| **GroupId** | string | 硬件隔离组id |No|
| **SpreadInfoSet** | array[[*SpreadInfo*](#SpreadInfo)] | 每个可用区中的机器数量。参见数据结构SpreadInfo。 |No|
| **Remark** | string | 备注 |No|

#### SpreadInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区信息 |No|
| **UHostCount** | int | 可用区中硬件隔离组中云主机的数量，不超过7。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeIsolationGroup
&Region=cn-zj
&GroupId=eoLEQOOy
&ProjectId=UAfwElsL
&Offset=4
&Limit=3
```

### 响应示例
    
```json
{
  "Action": "DescribeIsolationGroupResponse",
  "IsolationGroupSet": [
    {
      "GroupId": "sYCGPSVa",
      "GroupName": "FfjAvODP",
      "SpreadInfoSet": [
        {
          "UHostCount": 4,
          "Zone": "ckzKEzju"
        },
        {
          "UHostCount": 4,
          "Zone": "JxJjJLEh"
        },
        {
          "UHostCount": 1,
          "Zone": "vfeWwork"
        },
        {
          "UHostCount": 7,
          "Zone": "mdDSKRtP"
        },
        {
          "UHostCount": 8,
          "Zone": "ckmKtCkf"
        },
        {
          "UHostCount": 8,
          "Zone": "fdyQiLJX"
        },
        {
          "UHostCount": 6,
          "Zone": "bnpHtcVh"
        },
        {
          "UHostCount": 7,
          "Zone": "tlgxSexx"
        },
        {
          "UHostCount": 7,
          "Zone": "DknEPTTQ"
        }
      ]
    },
    {
      "GroupId": "dUtmePjp",
      "GroupName": "waQcuepq",
      "SpreadInfoSet": [
        {
          "UHostCount": 2,
          "Zone": "RIkhPcmF"
        },
        {
          "UHostCount": 6,
          "Zone": "ZZiDAcUQ"
        },
        {
          "UHostCount": 6,
          "Zone": "LxwjPKkC"
        },
        {
          "UHostCount": 6,
          "Zone": "EICjITTU"
        },
        {
          "UHostCount": 4,
          "Zone": "LvRzXMqO"
        },
        {
          "UHostCount": 1,
          "Zone": "hsNbrfIO"
        },
        {
          "UHostCount": 6,
          "Zone": "vLxZmVpQ"
        },
        {
          "UHostCount": 9,
          "Zone": "YaqMHcyT"
        },
        {
          "UHostCount": 8,
          "Zone": "VkTcAsom"
        },
        {
          "UHostCount": 7,
          "Zone": "osJUBzQs"
        }
      ]
    },
    {
      "GroupId": "PNbUMSnT",
      "GroupName": "BuRDNSMV",
      "SpreadInfoSet": [
        {
          "UHostCount": 1,
          "Zone": "FqzxOwWF"
        },
        {
          "UHostCount": 8,
          "Zone": "TYJXNABc"
        },
        {
          "UHostCount": 2,
          "Zone": "TmifjmqF"
        },
        {
          "UHostCount": 6,
          "Zone": "ynTmVgAX"
        },
        {
          "UHostCount": 3,
          "Zone": "VpulfwsB"
        },
        {
          "UHostCount": 8,
          "Zone": "GmkCwqKR"
        },
        {
          "UHostCount": 9,
          "Zone": "dDKSifpU"
        },
        {
          "UHostCount": 5,
          "Zone": "UrGHZufJ"
        },
        {
          "UHostCount": 5,
          "Zone": "gUdvtgFE"
        }
      ]
    },
    {
      "GroupId": "YRMkPcpS",
      "GroupName": "GLKfEBHo",
      "SpreadInfoSet": [
        {
          "UHostCount": 5,
          "Zone": "XHgsxqdg"
        },
        {
          "UHostCount": 6,
          "Zone": "iRQKLaRj"
        },
        {
          "UHostCount": 9,
          "Zone": "vFgPUUjt"
        },
        {
          "UHostCount": 4,
          "Zone": "BNWmMVpg"
        },
        {
          "UHostCount": 1,
          "Zone": "DeXHKBzt"
        },
        {
          "UHostCount": 9,
          "Zone": "avAFYxlI"
        },
        {
          "UHostCount": 3,
          "Zone": "sPwawXVS"
        },
        {
          "UHostCount": 7,
          "Zone": "XPOommle"
        },
        {
          "UHostCount": 8,
          "Zone": "sDVWXwoD"
        },
        {
          "UHostCount": 8,
          "Zone": "NHWKWBmr"
        }
      ]
    },
    {
      "GroupId": "KbqAWrnZ",
      "GroupName": "YQRxjUUP",
      "SpreadInfoSet": [
        {
          "UHostCount": 9,
          "Zone": "ybcvUHGg"
        },
        {
          "UHostCount": 2,
          "Zone": "bNCfdMfU"
        }
      ]
    },
    {
      "GroupId": "VvKIjAoJ",
      "GroupName": "PoNhklah",
      "SpreadInfoSet": [
        {
          "UHostCount": 1,
          "Zone": "jtsvJBwo"
        },
        {
          "UHostCount": 2,
          "Zone": "amlZMtpF"
        },
        {
          "UHostCount": 5,
          "Zone": "RqGIAweJ"
        },
        {
          "UHostCount": 2,
          "Zone": "ZUmCMgmh"
        },
        {
          "UHostCount": 7,
          "Zone": "DHLgKKsN"
        },
        {
          "UHostCount": 1,
          "Zone": "khBlCYDN"
        },
        {
          "UHostCount": 7,
          "Zone": "aKZoaKxv"
        },
        {
          "UHostCount": 7,
          "Zone": "XKwieRxS"
        },
        {
          "UHostCount": 1,
          "Zone": "ZztdlMSY"
        },
        {
          "UHostCount": 3,
          "Zone": "beGvpfXk"
        }
      ]
    },
    {
      "GroupId": "wYyaBPCv",
      "GroupName": "SPFppiav",
      "SpreadInfoSet": [
        {
          "UHostCount": 2,
          "Zone": "sHRTtqXY"
        },
        {
          "UHostCount": 6,
          "Zone": "IOyDEHtK"
        },
        {
          "UHostCount": 2,
          "Zone": "qCWALWUq"
        },
        {
          "UHostCount": 4,
          "Zone": "xWfLsowE"
        },
        {
          "UHostCount": 2,
          "Zone": "hpvNNHce"
        },
        {
          "UHostCount": 5,
          "Zone": "cJUybjFR"
        },
        {
          "UHostCount": 2,
          "Zone": "mVDidZHk"
        },
        {
          "UHostCount": 2,
          "Zone": "zbyPAXxR"
        },
        {
          "UHostCount": 6,
          "Zone": "PxaozvKP"
        },
        {
          "UHostCount": 5,
          "Zone": "BPfzdZlb"
        }
      ]
    },
    {
      "GroupId": "cILearzD",
      "GroupName": "GhNYJpke",
      "SpreadInfoSet": [
        {
          "UHostCount": 4,
          "Zone": "NlJbuwsv"
        },
        {
          "UHostCount": 6,
          "Zone": "JiDJVDmu"
        },
        {
          "UHostCount": 3,
          "Zone": "reyxDucL"
        },
        {
          "UHostCount": 5,
          "Zone": "BCanlmvA"
        },
        {
          "UHostCount": 4,
          "Zone": "ahWxmqUD"
        },
        {
          "UHostCount": 9,
          "Zone": "JxDibZhh"
        },
        {
          "UHostCount": 1,
          "Zone": "TjYOutYX"
        }
      ]
    },
    {
      "GroupId": "ppLfBQrd",
      "GroupName": "chrixSUu",
      "SpreadInfoSet": [
        {
          "UHostCount": 2,
          "Zone": "HPCwJiXb"
        },
        {
          "UHostCount": 4,
          "Zone": "QUqJKHmy"
        }
      ]
    },
    {
      "GroupId": "ZRjkgaqr",
      "GroupName": "UPZRkjRv",
      "SpreadInfoSet": [
        {
          "UHostCount": 1,
          "Zone": "CXNrjCEU"
        },
        {
          "UHostCount": 8,
          "Zone": "aYcMlSSf"
        },
        {
          "UHostCount": 9,
          "Zone": "gorleIqQ"
        },
        {
          "UHostCount": 2,
          "Zone": "WSpdvKHZ"
        }
      ]
    }
  ],
  "RetCode": 0
}
```





