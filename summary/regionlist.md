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



共计 **0** 个地域

| 地域短 ID | 地域名称 |
| ---:| ---:|


### 各可用区 (Zone) 名称列表



共计 **31** 个可用区

| 地域名称 | 可用区短 ID | 可用区名称 |
| --- | --- | --- |
| 华北一 | cn-bj2-02 | 华北一可用区B |
| 华北一 | cn-bj2-03 | 华北一可用区C |
| 华北一 | cn-bj2-04 | 华北一可用区D |
| 华北一 | cn-bj2-05 | 华北一可用区E |
| 广州 | cn-gd-02 | 广州可用区B |
| 福建 | cn-qz-01 | 福建GPU可用区A |
| 上海二 | cn-sh2-01 | 上海二可用区A |
| 上海二 | cn-sh2-02 | 上海二可用区B |
| 上海二 | cn-sh2-03 | 上海二可用区C |
| 华北二 | cn-wlcb-01 | 华北二可用区A |
| 拉各斯 | afr-nigeria-01 | 拉各斯可用区A |
| 圣保罗 | bra-saopaulo-01 | 圣保罗可用区A |
| 法兰克福 | ge-fra-01 | 法兰克福可用区A |
| 香港 | hk-01 | 香港可用区A |
| 香港 | hk-02 | 香港可用区B |
| 雅加达 | idn-jakarta-01 | 雅加达可用区A |
| 孟买 | ind-mumbai-01 | 孟买可用区A |
| 东京 | jpn-tky-01 | 东京可用区A |
| 首尔 | kr-seoul-01 | 首尔可用区A |
| 马尼拉 | ph-mnl-01 | 马尼拉可用区A |
| 莫斯科 | rus-mosc-01 | 莫斯科可用区A |
| 新加坡 | sg-01 | 新加坡可用区A |
| 新加坡 | sg-02 | 新加坡可用区B |
| 曼谷 | th-bkk-01 | 曼谷可用区A |
| 曼谷 | th-bkk-02 | 曼谷可用区B |
| 台北 | tw-tp-01 | 台北可用区A |
| 迪拜 | uae-dubai-01 | 迪拜可用区A |
| 伦敦 | uk-london-01 | 伦敦可用区A |
| 洛杉矶 | us-ca-01 | 洛杉矶可用区A |
| 华盛顿 | us-ws-01 | 华盛顿可用区A |
| 胡志明市 | vn-sng-01 | 胡志明市可用区A |

