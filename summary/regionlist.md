# 获取地域和可用区列表

UCloud 目前拥有多个地域（Region），遍布全球，每个地域下开设有多个可用区（Zone），用户在使用公有云相关的 API 发送操作指令时，需要指定指令所指向的地域。

## 查询方式

<!-- tabs:start -->

#### ** cURL **

?> 通过 cURL 发起请求需要手动计算签名，签名计算方法请参考 [签名算法](https://docs.ucloud.cn/api/summary/signature)，建议使用 CLI/SDK/UAPI 等工具发起查询，免去您计算签名的烦恼。

```bash
curl -X POST \
https://api.ucloud.cn \
-H 'Content-Type: application/json' \
-d '{
"Action":"GetRegion",
"PublicKey":"...",
"Signature":"..."
}'
```

#### ** CLI **

**安装**

可参考 [CLI 快速开始](https://docs.ucloud.cn/cli/intro)

**查询**

```bash
ucloud region list
```

#### ** UAPI **

UAPI 是 UCloud API 的在线浏览器，可以在线发起请求以及生成 SDK 样例。

访问 [UAPI](https://console.ucloud.cn/uapi/detail?id=GetRegion) 查询

<!-- tabs:end -->

API 文档可参考 [获取地域和可用区列表 - GetRegion](https://docs.ucloud.cn/api/uaccount-api/get_region) 页面。

## 地域和可用区列表

### 各地域 (Region) 名称列表



共计 **22** 个地域

| 地域短 ID | 地域名称 |
| --- | --- |
| cn-bj2 | 华北（北京2） |
| cn-gd | 华南（广州） |
| cn-qz | 华南（泉州） |
| cn-sh2 | 华东（上海2） |
| cn-wlcb | 华北（乌兰察布） |
| afr-nigeria | 尼日利亚（拉各斯） |
| bra-saopaulo | 巴西（圣保罗） |
| ge-fra | 德国（法兰克福） |
| hk | 香港 |
| idn-jakarta | 印度尼西亚（雅加达） |
| ind-mumbai | 印度（孟买） |
| jpn-tky | 日本（东京） |
| kr-seoul | 韩国（首尔） |
| ph-mnl | 菲律宾（马尼拉） |
| sg | 新加坡 |
| th-bkk | 泰国（曼谷） |
| tw-tp | 台湾（台北） |
| uae-dubai | 阿联酋（迪拜） |
| uk-london | 英国（伦敦） |
| us-ca | 美国（洛杉矶） |
| us-ws | 美国（华盛顿） |
| vn-sng | 越南（胡志明） |


### 各可用区 (Zone) 名称列表



共计 **30** 个可用区

| 地域名称 | 可用区短 ID | 可用区名称 |
| --- | --- | --- |
| 华北（北京2） | cn-bj2-02 | 华北（北京2）可用区B |
| 华北（北京2） | cn-bj2-03 | 华北（北京2）可用区C |
| 华北（北京2） | cn-bj2-04 | 华北（北京2） 可用区D |
| 华北（北京2） | cn-bj2-05 | 华北（北京2）可用区E |
| 华南（广州） | cn-gd-02 | 华南（广州）可用区B |
| 华南（泉州） | cn-qz-01 | 华南（泉州）可用区A |
| 华东（上海2） | cn-sh2-01 | 华东（上海2）可用区A |
| 华东（上海2） | cn-sh2-02 | 华东（上海2）可用区B |
| 华东（上海2） | cn-sh2-03 | 华东（上海2）可用区C |
| 华北（乌兰察布） | cn-wlcb-01 | 华北（乌兰察布）可用区A |
| 尼日利亚（拉各斯） | afr-nigeria-01 | 尼日利亚（拉各斯）可用区A |
| 巴西（圣保罗） | bra-saopaulo-01 | 巴西（圣保罗）可用区A |
| 德国（法兰克福） | ge-fra-01 | 德国（法兰克福）可用区A |
| 香港 | hk-01 | 香港可用区A |
| 香港 | hk-02 | 香港可用区B |
| 印度尼西亚（雅加达） | idn-jakarta-01 | 印度尼西亚（雅加达）可用区A |
| 印度（孟买） | ind-mumbai-01 | 印度（孟买）可用区A |
| 日本（东京） | jpn-tky-01 | 日本（东京）可用区A |
| 韩国（首尔） | kr-seoul-01 | 韩国（首尔）可用区A |
| 菲律宾（马尼拉） | ph-mnl-01 | 菲律宾（马尼拉）可用区A |
| 新加坡 | sg-01 | 新加坡可用区A |
| 新加坡 | sg-02 | 新加坡可用区B |
| 泰国（曼谷） | th-bkk-01 | 泰国（曼谷）可用区A |
| 泰国（曼谷） | th-bkk-02 | 泰国（曼谷）可用区B |
| 台湾（台北） | tw-tp-01 | 台湾（台北）可用区A |
| 阿联酋（迪拜） | uae-dubai-01 | 阿联酋（迪拜）可用区A |
| 英国（伦敦） | uk-london-01 | 英国（伦敦）可用区A |
| 美国（洛杉矶） | us-ca-01 | 美国（洛杉矶）可用区A |
| 美国（华盛顿） | us-ws-01 | 美国（华盛顿）可用区A |
| 越南（胡志明） | vn-sng-01 | 越南（胡志明）可用区A |

