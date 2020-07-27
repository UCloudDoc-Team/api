# 获取项目 ID

## 查询方式

<!-- tabs:start -->

#### ** cURL **

?> 通过 cURL 发起请求需要手动计算签名，签名计算方法请参考 [签名算法](https://docs.ucloud.cn/api/summary/signature)，建议使用 CLI/SDK/UAPI 等工具发起查询，免去您计算签名的烦恼。

```bash
curl -X POST \
  https://api.ucloud.cn \
  -H 'Content-Type: application/json' \
  -d '{
    "Action":"GetProjectList",
    "IsFinance":"Yes",
    "PublicKey":"...",
    "Signature":"..."
  }'
```

#### ** CLI **

**安装**

可参考 [CLI 快速开始](https://docs.ucloud.cn/cli/intro)

**查询**

```bash
ucloud project list
```

#### ** UAPI **

UAPI 是 UCloud API 的在线浏览器，可以在线发起请求以及生成 SDK 样例。

访问 [UAPI](https://console.ucloud.cn/uapi/detail?id=GetProjectList) 查询

<!-- tabs:end -->

API 文档可参考 [获取帐号下的项目列表 - GetProjectList](https://docs.ucloud.cn/api/uaccount-api/get_project_list) 页面。
