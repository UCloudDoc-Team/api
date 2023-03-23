# 获取全球加速线路信息 - DescribePathXLineConfig

## 简介

获取全球加速线路信息

?> 该接口返回了各条线路的线路ID 可用于创建新线路，以及各条线路可售的带宽最大值(会不定期调整 且区分预付费和后付费)




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribePathXLineConfig)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribePathXLineConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。不填为默认项目。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LineSet** | array[[*UGAALine*](#UGAALine)] | UGAA线路列表,参考UGAALine字段定义 |No|

#### 数据模型


#### UGAALine

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LineFrom** | string | 线路源 |**Yes**|
| **LineTo** | string | 线路目的 |**Yes**|
| **LineFromName** | string | 线路源中文名称 |**Yes**|
| **LineToName** | string | 线路目的中文名称 |**Yes**|
| **MaxBandwidth** | int | 预付费线路可售最大带宽 |**Yes**|
| **PostPaidMaxBandwidth** | int | 后付费线路最大可售带宽 |**Yes**|
| **GuaranteedBandwidthProportion** | int | 后付费线路上限带宽与保底带宽的固定比例，正整数 |**Yes**|
| **SupportPublicNetwork** | boolean | true:支持SD-WAN线路；false:不支持SD-WAN线路 |**Yes**|
| **LineId** | string | 线路ID，可用于创建加速线路资源 |**Yes**|
| **LineDetail** | array[[*LineDetail*](#LineDetail)] | 线路接入点信息 |**Yes**|
| **FlagUnicodeFrom** | string | 加速国家区域国旗代码 |**Yes**|
| **FlagUnicodeTo** | string | 源站所在国家区域国旗代码 |**Yes**|
| **RegionCategoryFrom** | string | 加速国家区域所属地区代码 |**Yes**|
| **RegionCategoryTo** | string | 源站所在国家区域所属地区代码 |**Yes**|

#### LineDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LineFrom** | string | 线路源 |**Yes**|
| **LineTo** | string | 线路目的 |**Yes**|
| **LineId** | string | 线路计费Id |No|
| **LineFromName** | string | 线路源中文名称 |**Yes**|
| **LineToName** | string | 线路目的中文名称 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribePathXLineConfig
&ProjectId=vtxLvmoV
```

### 响应示例
    
```json
{
  "Action": "DescribePathXLineConfigResponse",
  "LineSet": [
    {
      "LineDetail": [
        {
          "LineFrom": "afr-nigeria",
          "LineFromName": "拉各斯",
          "LineId": "line_afr-nigeria_cn-bj2",
          "LineTo": "cn-bj2",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "afr-nigeria",
      "LineFromName": "拉各斯",
      "LineId": "line_afr-nigeria_cn-bj2",
      "LineTo": "cn-bj2",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "afr-nigeria",
          "LineFromName": "拉各斯",
          "LineId": "line_afr-nigeria_ge-fra",
          "LineTo": "ge-fra",
          "LineToName": "法兰克福"
        }
      ],
      "LineFrom": "afr-nigeria",
      "LineFromName": "拉各斯",
      "LineId": "line_afr-nigeria_ge-fra",
      "LineTo": "ge-fra",
      "LineToName": "法兰克福"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "bra-saopaulo",
          "LineFromName": "圣保罗",
          "LineId": "line_bra-saopaulo_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "bra-saopaulo",
      "LineFromName": "圣保罗",
      "LineId": "line_bra-saopaulo_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国",
          "LineId": "line_cn-bj2_ge-fra",
          "LineTo": "ge-fra",
          "LineToName": "法兰克福"
        }
      ],
      "LineFrom": "cn-bj2",
      "LineFromName": "中国",
      "LineId": "line_cn-bj2_ge-fra",
      "LineTo": "ge-fra",
      "LineToName": "法兰克福"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国",
          "LineId": "line_cn-bj2_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "cn-bj2",
      "LineFromName": "中国",
      "LineId": "line_cn-bj2_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国",
          "LineId": "line_cn-gd_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国",
      "LineId": "line_cn-gd_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_ge-fra",
          "LineTo": "ge-fra",
          "LineToName": "法兰克福"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_ge-fra",
          "LineTo": "ge-fra",
          "LineToName": "法兰克福"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_ge-fra",
          "LineTo": "ge-fra",
          "LineToName": "法兰克福"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn-ge-fra",
      "LineTo": "ge-fra",
      "LineToName": "法兰克福"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn-hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn-us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_afr-nigeria",
          "LineTo": "afr-nigeria",
          "LineToName": "拉各斯"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_afr-nigeria",
          "LineTo": "afr-nigeria",
          "LineToName": "拉各斯"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_afr-nigeria",
          "LineTo": "afr-nigeria",
          "LineToName": "拉各斯"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_afr-nigeria",
      "LineTo": "afr-nigeria",
      "LineToName": "拉各斯"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_idn-jakarta",
          "LineTo": "idn-jakarta",
          "LineToName": "雅加达"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_idn-jakarta",
          "LineTo": "idn-jakarta",
          "LineToName": "雅加达"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_idn-jakarta",
          "LineTo": "idn-jakarta",
          "LineToName": "雅加达"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_idn-jakarta",
      "LineTo": "idn-jakarta",
      "LineToName": "雅加达"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_ind-mumbai",
          "LineTo": "ind-mumbai",
          "LineToName": "孟买"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_ind-mumbai",
          "LineTo": "ind-mumbai",
          "LineToName": "孟买"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_ind-mumbai",
          "LineTo": "ind-mumbai",
          "LineToName": "孟买"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_ind-mumbai",
      "LineTo": "ind-mumbai",
      "LineToName": "孟买"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_jpn-tky",
          "LineTo": "jpn-tky",
          "LineToName": "东京"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_jpn-tky",
          "LineTo": "jpn-tky",
          "LineToName": "东京"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_jpn-tky",
          "LineTo": "jpn-tky",
          "LineToName": "东京"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_jpn-tky",
      "LineTo": "jpn-tky",
      "LineToName": "东京"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_sg",
      "LineTo": "sg",
      "LineToName": "新加坡"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_th-bkk",
          "LineTo": "th-bkk",
          "LineToName": "曼谷"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_th-bkk",
          "LineTo": "th-bkk",
          "LineToName": "曼谷"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_th-bkk",
          "LineTo": "th-bkk",
          "LineToName": "曼谷"
        }
      ],
      "LineFrom": "cn-bj2",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_th-bkk",
      "LineTo": "th-bkk",
      "LineToName": "曼谷"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_tw-tp",
          "LineTo": "tw-tp",
          "LineToName": "中国台北"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_tw-tp",
          "LineTo": "tw-tp",
          "LineToName": "中国台北"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_tw-tp",
          "LineTo": "tw-tp",
          "LineToName": "中国台北"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_tw-tp",
      "LineTo": "tw-tp",
      "LineToName": "中国台北"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "cn-bj2",
          "LineFromName": "中国华北",
          "LineId": "line_cn-bj2_us-ws",
          "LineTo": "us-ws",
          "LineToName": "华盛顿"
        },
        {
          "LineFrom": "cn-gd",
          "LineFromName": "中国华南",
          "LineId": "line_cn-gd_us-ws",
          "LineTo": "us-ws",
          "LineToName": "华盛顿"
        },
        {
          "LineFrom": "cn-sh2",
          "LineFromName": "中国华东",
          "LineId": "line_cn-sh2_us-ws",
          "LineTo": "us-ws",
          "LineToName": "华盛顿"
        }
      ],
      "LineFrom": "cn-gd",
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_us-ws",
      "LineTo": "us-ws",
      "LineToName": "华盛顿"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ge-fra",
          "LineFromName": "法兰克福",
          "LineId": "line_ge-fra_cn-bj2",
          "LineTo": "cn-bj2",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "ge-fra",
      "LineFromName": "法兰克福",
      "LineId": "line_ge-fra_cn-bj2",
      "LineTo": "cn-bj2",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ge-fra",
          "LineFromName": "法兰克福",
          "LineId": "line_ge-fra_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "ge-fra",
      "LineFromName": "法兰克福",
      "LineId": "line_ge-fra_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ge-fra",
          "LineFromName": "法兰克福",
          "LineId": "line_ge-fra_jpn-tky",
          "LineTo": "jpn-tky",
          "LineToName": "东京"
        }
      ],
      "LineFrom": "ge-fra",
      "LineFromName": "法兰克福",
      "LineId": "line_ge-fra_jpn-tky",
      "LineTo": "jpn-tky",
      "LineToName": "东京"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ge-fra",
          "LineFromName": "法兰克福",
          "LineId": "line_ge-fra_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        }
      ],
      "LineFrom": "ge-fra",
      "LineFromName": "法兰克福",
      "LineId": "line_ge-fra_sg",
      "LineTo": "sg",
      "LineToName": "新加坡"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ge-fra",
          "LineFromName": "法兰克福",
          "LineId": "line_ge-fra_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "ge-fra",
      "LineFromName": "法兰克福",
      "LineId": "line_ge-fra_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ge-fra",
          "LineFromName": "法兰克福",
          "LineId": "line_ge-fra_us-ws",
          "LineTo": "us-ws",
          "LineToName": "华盛顿"
        }
      ],
      "LineFrom": "ge-fra",
      "LineFromName": "法兰克福",
      "LineId": "line_ge-fra_us-ws",
      "LineTo": "us-ws",
      "LineToName": "华盛顿"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_cn-gd",
          "LineTo": "cn-gd",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_cn-gd",
      "LineTo": "cn-gd",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_ge-fra",
          "LineTo": "ge-fra",
          "LineToName": "法兰克福"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_ge-fra",
      "LineTo": "ge-fra",
      "LineToName": "法兰克福"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_idn-jakarta",
          "LineTo": "idn-jakarta",
          "LineToName": "雅加达"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_idn-jakarta",
      "LineTo": "idn-jakarta",
      "LineToName": "雅加达"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_ind-mumbai",
          "LineTo": "ind-mumbai",
          "LineToName": "孟买"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_ind-mumbai",
      "LineTo": "ind-mumbai",
      "LineToName": "孟买"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_jpn-tky",
          "LineTo": "jpn-tky",
          "LineToName": "东京"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_jpn-tky",
      "LineTo": "jpn-tky",
      "LineToName": "东京"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_sg",
      "LineTo": "sg",
      "LineToName": "新加坡"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_th-bkk",
          "LineTo": "th-bkk",
          "LineToName": "曼谷"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_th-bkk",
      "LineTo": "th-bkk",
      "LineToName": "曼谷"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_tw-tp",
          "LineTo": "tw-tp",
          "LineToName": "中国台北"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_tw-tp",
      "LineTo": "tw-tp",
      "LineToName": "中国台北"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "hk",
          "LineFromName": "亚太",
          "LineId": "line_hk_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "hk",
      "LineFromName": "中国香港",
      "LineId": "line_hk_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "idn-jakarta",
          "LineFromName": "雅加达",
          "LineId": "line_idn-jakarta_cn-gd",
          "LineTo": "cn-gd",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "idn-jakarta",
      "LineFromName": "雅加达",
      "LineId": "line_idn-jakarta_cn-gd",
      "LineTo": "cn-gd",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "idn-jakarta",
          "LineFromName": "雅加达",
          "LineId": "line_idn-jakarta_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "idn-jakarta",
      "LineFromName": "雅加达",
      "LineId": "line_idn-jakarta_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "idn-jakarta",
          "LineFromName": "亚太",
          "LineId": "line_idn-jakarta_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        }
      ],
      "LineFrom": "idn-jakarta",
      "LineFromName": "雅加达",
      "LineId": "line_idn-jakarta_sg",
      "LineTo": "sg",
      "LineToName": "新加坡"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ind-mumbai",
          "LineFromName": "孟买",
          "LineId": "line_ind-mumbai_cn-gd",
          "LineTo": "cn-gd",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "ind-mumbai",
      "LineFromName": "孟买",
      "LineId": "line_ind-mumbai_cn-gd",
      "LineTo": "cn-gd",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ind-mumbai",
          "LineFromName": "孟买",
          "LineId": "line_ind-mumbai_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "ind-mumbai",
      "LineFromName": "孟买",
      "LineId": "line_ind-mumbai_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ind-mumbai",
          "LineFromName": "孟买",
          "LineId": "line_ind-mumbai_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        }
      ],
      "LineFrom": "ind-mumbai",
      "LineFromName": "孟买",
      "LineId": "line_ind-mumbai_sg",
      "LineTo": "sg",
      "LineToName": "新加坡"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "ind-mumbai",
          "LineFromName": "孟买",
          "LineId": "line_ind-mumbai_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "ind-mumbai",
      "LineFromName": "孟买",
      "LineId": "line_ind-mumbai_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "jpn-tky",
          "LineFromName": "东京",
          "LineId": "line_jpn-tky_cn-sh2",
          "LineTo": "cn-sh2",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "jpn-tky",
      "LineFromName": "东京",
      "LineId": "line_jpn-tky_cn-sh2",
      "LineTo": "cn-sh2",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "jpn-tky",
          "LineFromName": "东京",
          "LineId": "line_jpn-tky_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "jpn-tky",
      "LineFromName": "东京",
      "LineId": "line_jpn-tky_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "jpn-tky",
          "LineFromName": "东京",
          "LineId": "line_jpn-tky_kr-seoul",
          "LineTo": "kr-seoul",
          "LineToName": "首尔"
        }
      ],
      "LineFrom": "jpn-tky",
      "LineFromName": "东京",
      "LineId": "line_jpn-tky_kr-seoul",
      "LineTo": "kr-seoul",
      "LineToName": "首尔"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "jpn-tky",
          "LineFromName": "东京",
          "LineId": "line_jpn-tky_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "jpn-tky",
      "LineFromName": "东京",
      "LineId": "line_jpn-tky_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "kr-seoul",
          "LineFromName": "首尔",
          "LineId": "line_kr-seoul_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "kr-seoul",
      "LineFromName": "首尔",
      "LineId": "line_kr-seoul_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "sg",
          "LineFromName": "U新加坡",
          "LineId": "line_sg_cn-gd",
          "LineTo": "cn-gd",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "sg",
      "LineFromName": "新加坡",
      "LineId": "line_sg_cn-gd",
      "LineTo": "cn-gd",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "sg",
          "LineFromName": "U新加坡",
          "LineId": "line_sg_ge-fra",
          "LineTo": "ge-fra",
          "LineToName": "法兰克福"
        }
      ],
      "LineFrom": "sg",
      "LineFromName": "新加坡",
      "LineId": "line_sg_ge-fra",
      "LineTo": "ge-fra",
      "LineToName": "法兰克福"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "sg",
          "LineFromName": "U新加坡",
          "LineId": "line_sg_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "sg",
      "LineFromName": "新加坡",
      "LineId": "line_sg_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "sg",
          "LineFromName": "U新加坡",
          "LineId": "line_sg_idn-jakarta",
          "LineTo": "idn-jakarta",
          "LineToName": "雅加达"
        }
      ],
      "LineFrom": "sg",
      "LineFromName": "新加坡",
      "LineId": "line_sg_idn-jakarta",
      "LineTo": "idn-jakarta",
      "LineToName": "雅加达"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "sg",
          "LineFromName": "U新加坡",
          "LineId": "line_sg_ind-mumbai",
          "LineTo": "ind-mumbai",
          "LineToName": "孟买"
        }
      ],
      "LineFrom": "sg",
      "LineFromName": "新加坡",
      "LineId": "line_sg_ind-mumbai",
      "LineTo": "ind-mumbai",
      "LineToName": "孟买"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "sg",
          "LineFromName": "U新加坡",
          "LineId": "line_sg_th-bkk",
          "LineTo": "th-bkk",
          "LineToName": "曼谷"
        }
      ],
      "LineFrom": "sg",
      "LineFromName": "新加坡",
      "LineId": "line_sg_th-bkk",
      "LineTo": "th-bkk",
      "LineToName": "曼谷"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "sg",
          "LineFromName": "U新加坡",
          "LineId": "line_sg_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "sg",
      "LineFromName": "新加坡",
      "LineId": "line_sg_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "th-bkk",
          "LineFromName": "曼谷",
          "LineId": "line_th-bkk_cn-gd",
          "LineTo": "cn-gd",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "th-bkk",
      "LineFromName": "曼谷",
      "LineId": "line_th-bkk_cn-gd",
      "LineTo": "cn-gd",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "th-bkk",
          "LineFromName": "曼谷",
          "LineId": "line_th-bkk_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "th-bkk",
      "LineFromName": "曼谷",
      "LineId": "line_th-bkk_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "th-bkk",
          "LineFromName": "曼谷",
          "LineId": "line_th-bkk_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        }
      ],
      "LineFrom": "th-bkk",
      "LineFromName": "曼谷",
      "LineId": "line_th-bkk_sg",
      "LineTo": "sg",
      "LineToName": "新加坡"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "tw-tp",
          "LineFromName": "中国台北",
          "LineId": "line_tw-tp_cn-gd",
          "LineTo": "cn-gd",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "tw-tp",
      "LineFromName": "中国台北",
      "LineId": "line_tw-tp_cn-gd",
      "LineTo": "cn-gd",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "tw-tp",
          "LineFromName": "中国台北",
          "LineId": "line_tw-tp_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "tw-tp",
      "LineFromName": "中国台北",
      "LineId": "line_tw-tp_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "tw-tp",
          "LineFromName": "中国台北",
          "LineId": "line_tw-tp_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        }
      ],
      "LineFrom": "tw-tp",
      "LineFromName": "中国台北",
      "LineId": "line_tw-tp_sg",
      "LineTo": "sg",
      "LineToName": "新加坡"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "tw-tp",
          "LineFromName": "中国台北",
          "LineId": "line_tw-tp_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "tw-tp",
      "LineFromName": "中国台北",
      "LineId": "line_tw-tp_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ca",
          "LineFromName": "洛杉矶",
          "LineId": "line_us-ca_cn-bj2",
          "LineTo": "cn-bj2",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "us-ca",
      "LineFromName": "洛杉矶",
      "LineId": "line_us-ca_cn-bj2",
      "LineTo": "cn-bj2",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ca",
          "LineFromName": "洛杉矶",
          "LineId": "line_us-ca_hk",
          "LineTo": "hk",
          "LineToName": "中国香港"
        }
      ],
      "LineFrom": "us-ca",
      "LineFromName": "洛杉矶",
      "LineId": "line_us-ca_hk",
      "LineTo": "hk",
      "LineToName": "中国香港"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ca",
          "LineFromName": "洛杉矶",
          "LineId": "line_us-ca_ind-mumbai",
          "LineTo": "ind-mumbai",
          "LineToName": "孟买"
        }
      ],
      "LineFrom": "us-ca",
      "LineFromName": "洛杉矶",
      "LineId": "line_us-ca_ind-mumbai",
      "LineTo": "ind-mumbai",
      "LineToName": "孟买"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ca",
          "LineFromName": "洛杉矶",
          "LineId": "line_us-ca_jpn-tky",
          "LineTo": "jpn-tky",
          "LineToName": "东京"
        }
      ],
      "LineFrom": "us-ca",
      "LineFromName": "洛杉矶",
      "LineId": "line_us-ca_jpn-tky",
      "LineTo": "jpn-tky",
      "LineToName": "东京"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ca",
          "LineFromName": "洛杉矶",
          "LineId": "line_us-ca_sg",
          "LineTo": "sg",
          "LineToName": "新加坡"
        }
      ],
      "LineFrom": "us-ca",
      "LineFromName": "洛杉矶",
      "LineId": "line_us-ca_sg",
      "LineTo": "sg",
      "LineToName": "新加坡"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ca",
          "LineFromName": "洛杉矶",
          "LineId": "line_us-ca_us-ws",
          "LineTo": "us-ws",
          "LineToName": "华盛顿"
        }
      ],
      "LineFrom": "us-ca",
      "LineFromName": "洛杉矶",
      "LineId": "line_us-ca_us-ws",
      "LineTo": "us-ws",
      "LineToName": "华盛顿"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ws",
          "LineFromName": "华盛顿",
          "LineId": "line_us-ws_cn-bj2",
          "LineTo": "cn-bj2",
          "LineToName": "中国"
        }
      ],
      "LineFrom": "us-ws",
      "LineFromName": "华盛顿",
      "LineId": "line_us-ws_cn-bj2",
      "LineTo": "cn-bj2",
      "LineToName": "中国"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ws",
          "LineFromName": "华盛顿",
          "LineId": "line_us-ws_ge-fra",
          "LineTo": "ge-fra",
          "LineToName": "法兰克福"
        }
      ],
      "LineFrom": "us-ws",
      "LineFromName": "华盛顿",
      "LineId": "line_us-ws_ge-fra",
      "LineTo": "ge-fra",
      "LineToName": "法兰克福"
    },
    {
      "LineDetail": [
        {
          "LineFrom": "us-ws",
          "LineFromName": "华盛顿",
          "LineId": "line_us-ws_us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶"
        }
      ],
      "LineFrom": "us-ws",
      "LineFromName": "华盛顿",
      "LineId": "line_us-ws_us-ca",
      "LineTo": "us-ca",
      "LineToName": "洛杉矶"
    }
  ],
  "Message": "",
  "RetCode": 0
}
```





