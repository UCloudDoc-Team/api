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





共计 **0** 个地域

| 地域短 ID | 地域名称 |
| ---:| ---:|


### 各可用区 (Zone) 名称列表





共计 **0** 个可用区

| 可用区短 ID | 可用区名称 |
| ---:| ---:|

