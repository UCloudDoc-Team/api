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
"Action":"ListRegions",
"PublicKey":"...",
"Signature":"..."
}'
```

```bash
curl -X POST \
https://api.ucloud.cn \
-H 'Content-Type: application/json' \
-d '{
"Action":"ListZones",
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

访问 [UAPI](https://console.ucloud.cn/uapi/detail?id=ListRegions) 查询

<!-- tabs:end -->

API 文档可参考

- [获取地域列表 - ListRegions](https://docs.ucloud.cn/api/uaccount-api/list_regions) 页面。
- [获取可用区列表 - ListZones](https://docs.ucloud.cn/api/uaccount-api/list_zones) 页面。

## 地域和可用区列表

### 各地域 (Region) 名称列表





共计 **33** 个地域

| 地域短 ID | 地域名称 |
| --- | --- |
| cn-bj1 | 华北（北京） |
| cn-bj2 | 华北（北京2） |
| cn-wlcb | 华北（乌兰察布） |
| cn-wlcb2 | 华北（乌兰察布2） |
| cn-sh2 | 华东（上海2） |
| cn-jx | 华东（嘉兴） |
| cn-sh | 金融云-华东（上海） |
| cn-gd2 | 华南（广州2） |
| cn-gd | 华南（广州） |
| cn-guiyang1 | 西南（贵阳） |
| hk | 香港 |
| tw-tp | 台湾（台北） |
| sg | 新加坡 |
| jpn-tky | 日本（东京） |
| kr-seoul | 韩国（首尔） |
| th-bkk | 泰国（曼谷） |
| idn-jakarta | 印度尼西亚（雅加达） |
| vn-sng | 越南（胡志明） |
| ph-mnl | 菲律宾（马尼拉） |
| ind-mumbai | 印度（孟买） |
| pk-khi | 巴基斯坦（卡拉奇） |
| us-den | 美国（丹佛） |
| us-ca | 美国（洛杉矶） |
| us-ws | 美国（华盛顿） |
| bra-saopaulo | 巴西（圣保罗） |
| rus-mosc | 俄罗斯（莫斯科） |
| ge-fra | 德国（法兰克福） |
| uk-london | 英国（伦敦） |
| uae-dubai | 阿联酋（迪拜） |
| afr-nigeria | 尼日利亚（拉各斯） |
| uz-tas | 乌兹别克斯坦（塔什干） |
| kz-ala | 哈萨克斯坦（阿拉木图） |
| mx-mex | 墨西哥（墨西哥城） |


### 各可用区 (Zone) 名称列表





共计 **42** 个可用区

| 可用区短 ID | 可用区名称 |
| --- | --- |
| cn-bj1-01 | 华北（北京）可用区A |
| hk-02 | 香港可用区B |
| cn-bj2-02 | 华北（北京2）可用区B |
| cn-bj2-03 | 华北（北京2）可用区C |
| us-ca-01 | 美国（洛杉矶）可用区A |
| cn-gd-02 | 华南（广州）可用区B |
| cn-gd2-01 | 华南（广州2）可用区A |
| cn-sh-01 | 金融云-华东（上海）可用区A |
| cn-sh-02 | 金融云-华东（上海）可用区B |
| cn-sh-03 | 金融云-华东（上海）可用区C |
| cn-sh2-01 | 华东（上海2）可用区A |
| cn-sh2-02 | 华东（上海2）可用区B |
| cn-sh2-03 | 华东（上海2）可用区C |
| cn-bj2-05 | 华北（北京2）可用区E |
| us-ws-01 | 美国（华盛顿）可用区A |
| ge-fra-01 | 德国（法兰克福）可用区A |
| kr-seoul-01 | 韩国（首尔）可用区A |
| sg-01 | 新加坡可用区A |
| rus-mosc-01 | 俄罗斯（莫斯科）可用区A |
| jpn-tky-01 | 日本（东京）可用区A |
| tw-tp-01 | 台湾（台北）可用区A |
| uae-dubai-01 | 阿联酋（迪拜）可用区A |
| idn-jakarta-01 | 印度尼西亚（雅加达）可用区A |
| ind-mumbai-01 | 印度（孟买）可用区A |
| bra-saopaulo-01 | 巴西（圣保罗）可用区A |
| uk-london-01 | 英国（伦敦）可用区A |
| afr-nigeria-01 | 尼日利亚（拉各斯）可用区A |
| vn-sng-01 | 越南（胡志明）可用区A |
| cn-jx-01 | 华东（嘉兴）可用区A |
| ph-mnl-01 | 菲律宾（马尼拉）可用区A |
| th-bkk-02 | 泰国（曼谷）可用区B |
| cn-wlcb-01 | 华北（乌兰察布）可用区A |
| sg-02 | 新加坡可用区B |
| cn-wlcb2-01 | 华北（乌兰察布2）可用区A |
| cn-wlcb-03 | 华北（乌兰察布）可用区C |
| cn-guiyang1-01 | 西南（贵阳）可用区A |
| us-den-01 | 美国（丹佛）可用区A |
| pk-khi-01 | 巴基斯坦（卡拉奇）可用区A |
| rus-mosc-02 | 俄罗斯（莫斯科）可用区B |
| uz-tas-01 | 乌兹别克斯坦（塔什干）可用区A |
| kz-ala-01 | 哈萨克斯坦（阿拉木图）可用区A |
| mx-mex-01 | 墨西哥（墨西哥城）可用区A |

